## Benchmarks

**BenchmarkDotNet v0.15.4**  
**OS:** Windows 10 (10.0.19044.5247 / 21H2 / November 2021 Update)  
**CPU:** AMD Ryzen 9 7900X 4.70 GHz — 1 CPU, 24 logical / 12 physical cores  
**.NET SDK:** 10.0.100-rc.1.25451.107  
**Job:** DefaultJob — .NET 10.0.0  
**Runtime:** 10.0.0-rc.1.25451.107, 10.0.25.45207, X64 RyuJIT x86-64-v4

----

#### Version 2025-09-28


| Method     | Mean     | Error    | StdDev   | Allocated |
|----------- |---------:|---------:|---------:|----------:|
| GetValue   | 134.6 ns | 1.48 ns  | 1.31 ns  |     440 B |
| SetValue   | 44.39 µs | 0.834 µs | 0.893 µs |  17.34 KB |
| SetMillion | 4.857 s  | 0.0198 s | 0.0185 s |  12.13 GB |


#### Version 2025-09-30

| Method     | Mean     | Error    | StdDev   | Allocated |
|----------- |---------:|---------:|---------:|----------:|
| GetValue   | 56.71 ns | 0.532 ns | 0.472 ns |      32 B |
| SetValue   | 31.38 µs | 0.459 µs | 0.383 µs |  13.68 KB |
| SetMillion | 1.711 s  | 0.0163 s | 0.0144 s |  10.76 GB |

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
```