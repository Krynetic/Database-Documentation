## Benchmarks

**BenchmarkDotNet v0.15.4**  
**OS:** Windows 10 (10.0.19044.5247 / 21H2 / November 2021 Update)  
**CPU:** AMD Ryzen 9 7900X 4.70 GHz � 1 CPU, 24 logical / 12 physical cores  
**.NET SDK:** 10.0.100-rc.1.25451.107  
**Job:** DefaultJob � .NET 10.0.0  
**Runtime:** 10.0.0-rc.1.25451.107, 10.0.25.45207, X64 RyuJIT x86-64-v4

----

#### Version 2025-09-28


| Method     | Mean     | Error    | StdDev   | Allocated |
|----------- |---------:|---------:|---------:|----------:|
| GetValue   | 134.6 ns | 1.48 ns  | 1.31 ns  |     440 B |
| SetValue   | 44.39 �s | 0.834 �s | 0.893 �s |  17.34 KB |
| SetMillion | 4.857 s  | 0.0198 s | 0.0185 s |  12.13 GB |


#### Version 2025-09-30

| Method     | Mean     | Error    | StdDev   | Allocated |
|----------- |---------:|---------:|---------:|----------:|
| GetValue   | 56.71 ns | 0.532 ns | 0.472 ns |      32 B |
| SetValue   | 31.38 �s | 0.459 �s | 0.383 �s |  13.68 KB |
| SetMillion | 1.711 s  | 0.0163 s | 0.0144 s |  10.76 GB |

#### Version 2025-10-01 #1

| Method     | Mean     | Error    | StdDev   | Allocated |
|---------   |---------:|---------:|---------:|----------:|
| GetValue   | 53.80 ns | 5.366 ns | 0.294 ns |      32 B |
| SetValue   | 29.27 �s | 28.98 �s | 1.589 �s |   6.79 KB |
| SetMillion | 1.166 s  | 0.3686 s | 0.0202 s |   4.19 GB |

#### Version 2025-10-01 #2

| Method     | Mean     | Error    | StdDev   | Allocated |
|----------- |---------:|---------:|---------:|----------:|
| GetValue   | 17.01 ns | 6.442 ns | 0.353 ns |      32 B |
| SetValue   | 12.40 �s | 6.578 �s | 0.361 �s |    3.5 KB |
| SetMillion | 819.8 ms | 226.5 ms | 12.42 ms |   3.23 GB |

#### Version 2025-10-02

| Method       | Mean     | Error    | StdDev   | Allocated |
|-----------   |---------:|---------:|--------: |----------:|
| GetValue     | 17.13 ns | 0.824 ns | 0.045 ns |      32 B |
| SetValue     | 10.80 �s | 3.649 �s | 0.200 �s |   3.14 KB |
| SetMillion   | 649.6 ms | 135.6 ms | 7.43 ms  |   2.87 GB |
| RandomSet    | 15.91 �s | 0.268 �s | 1.363 �s |    7.9 KB |
| RandomSet10K | 23.21 ms | 0.388 ms | 1.993 ms |  65.17 MB |

#### Version 2025-10-20

| Method       | Mean     | Error    | StdDev   | Allocated |
|-----------   |---------:|---------:|--------: |----------:|
| GetValue     | 23.50 ns | 0.584 ns | 0.875 ns |      72 B |
| SetValue     | 11.29 �s | 0.675 �s | 0.969 �s |   2.65 KB |
| SetMillion   | 670.1 ms | 42.57 ms | 2.33 ms  |   2.47 GB |
| RandomSet    | 14.01 �s | 0.248 �s | 1.235 �s |   5.49 KB |
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