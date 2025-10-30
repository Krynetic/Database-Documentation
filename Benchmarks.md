## Benchmarks

**BenchmarkDotNet v0.15.4**  
**OS:** Windows 10 (10.0.19044.5247 / 21H2 / November 2021 Update)  
**CPU:** AMD Ryzen 9 7900X 4.70 GHz — 1 CPU, 24 logical / 12 physical cores  
**.NET SDK:** 10.0.100-rc.1.25451.107  
**Job:** DefaultJob — .NET 10.0.0  
**Runtime:** 10.0.0-rc.1.25451.107, 10.0.25.45207, X64 RyuJIT x86-64-v4

----

#### Version 2025-10-20

| Method       | Mean     | Error    | StdDev   | Allocated |
|-----------   |---------:|---------:|--------: |----------:|
| GetValue     | 23.50 ns | 0.584 ns | 0.875 ns |      72 B |
| SetValue     | 11.29 µs | 0.675 µs | 0.969 µs |   2.65 KB |
| SetMillion   | 670.1 ms | 42.57 ms | 2.33 ms  |   2.47 GB |
| RandomSet    | 14.01 µs | 0.248 µs | 1.235 µs |   5.49 KB |
| RandomSet10K | 14.74 ms | 0.258 ms | 1.307 ms |   41.5 MB |

---

**Code**
```csharp
[GlobalSetup]
public void Setup()
{
    store = KryneticStore.Temporary();
    store["static"] = "1";
}

[Benchmark]
public void SetMillion()
{
    for (int i = 0; i < 1_000_000; i++)
    {
        store[i.ToString()] = new { name = "bench", age = 100 };
    }
}

[IterationSetup(Target = nameof(SetValue))]
public void Reset()
{
    store["value"] = new { name = (string?)null, age = 0 };
}

[Benchmark]
public void SetValue()
{
    store["value"] = new { name = "bench", age = 100 };
}

[Benchmark]
public object? GetValue()
{
    return store["static"];
}

[IterationSetup(Target = nameof(RandomSet))]
public void RandomSet_Reset() => store.Clear();

[Benchmark]
public void RandomSet()
{
    store["folder1/folder2/" + prng.Long()] = new
    {
        name = "name" + prng.Long(),
        age = prng.Long()
    };
}

[IterationSetup(Target = nameof(RandomSet10K))]
public void RandomSet10K_Reset() => store.Clear();

[Benchmark]
public void RandomSet10K()
{
    for (int i = 0; i < 10_000; i++)
    {
        store["folder1/folder2/" + prng.Long()] = new
        {
            name = "name" + prng.Long(),
            age = prng.Long()
        };
    }
}
```

---

## Request benchmarks

**NOTE**: <span style="color:red">Intra-docker container execution - Benchmarker is started within docker container</span> !

### Krynetic start arguments used

--server openapi \
--optimize-socket \
--loglevel information \
--prefill

---

### *Latency*: 0.9 ms

```csharp
#https://search.apps.ubuntu.com/api/v1/package/wrk2
wrk -t32 -c128 -R 1000 -d15s  http://localhost:8080/static
```

```text
Running 15s test @ http://localhost:8080/static
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency     0.90ms  518.66us   8.10ms   71.11%
    Req/Sec    32.38     70.90   333.00     86.53%
  15136 requests in 15.11s, 2.46MB read
Requests/sec:   1002.01
Transfer/sec:    166.51KB
```

### *Requests per seconds*: 95,000 (WRK 2)

```csharp
#https://search.apps.ubuntu.com/api/v1/package/wrk2
wrk -t32 -c128 -R 100000 -d15s  http://localhost:8080/static
```

```text
Running 15s test @ http://localhost:8080/static
  1423862 requests in 14.99s, 231.10MB read
Requests/sec:  94957.03
Transfer/sec:  15.41MB
```


###  *Requests per seconds*: 80,700 (Bombardier)

```csharp
#v2.0.2/bombardier-linux-amd64
bombardier --connections 128 --duration 5s --latencies --disableKeepAlives http://localhost:8080/static
```

```text
Statistics        Avg      Stdev        Max
  Reqs/sec     80731.91    9670.01  108452.31
  Latency        1.58ms   513.38us    15.39ms
  Latency Distribution
     50%     1.18ms
     75%     1.91ms
     90%     3.29ms
     95%     3.89ms
     99%     5.58ms
  HTTP codes:
    1xx - 0, 2xx - 403854, 3xx - 0, 4xx - 0, 5xx - 0
    others - 0
  Throughput:    18.33MB/s
```

 ### *Throughput*: 2.1 GB/s (apache2-utils)

 ```csharp
#apache2-utils/now 2.4.65-1~deb12u1 amd64
ab -n10000 -c64 http://localhost:8080/static_1M
```

 ```text
This is ApacheBench, Version 2.3 <$Revision: 1923142 $>
Copyright 1996 Adam Twiss, Zeus Technology Ltd, http://www.zeustech.net/
Licensed to The Apache Software Foundation, http://www.apache.org/

Server Software:        Microsoft-NetCore/2.0
Server Hostname:        localhost
Server Port:            8080

Document Path:          /static_1M
Document Length:        1000002 bytes

Concurrency Level:      64
Time taken for tests:   4.632 seconds
Complete requests:      10000
Failed requests:        0
Total transferred:      10001400000 bytes
HTML transferred:       10000020000 bytes
Requests per second:    2158.82 [#/sec] (mean)
Time per request:       29.646 [ms] (mean)
Time per request:       0.463 [ms] (mean, across all concurrent requests)
Transfer rate:          2108518.34 [Kbytes/sec] received

Connection Times (ms)
              min  mean[+/-sd] median   max
Connect:        0    1   0.2      1       3
Processing:    11   29   1.4     29      36
Waiting:        0    1   0.8      1       7
Total:         11   30   1.4     29      37

Percentage of the requests served within a certain time (ms)
  50%     29
  66%     30
  75%     30
  80%     30
  90%     31
  95%     32
  98%     33
  99%     34
 100%     37 (longest request)
 ```
