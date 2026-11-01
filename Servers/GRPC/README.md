# gRPC

**Default endpoint:** `http://localhost:50051` (HTTP/2 without TLS) · **Server name:** `GRPC`

```bash
Krynetic.Database --server GRPC
```

## Protobuf contract

Download [`krynetic.proto`](krynetic.proto) (also shown below) and generate a client in your language.

```protobuf
syntax = "proto3";

option optimize_for = SPEED;
option java_package = "com.krynetic";
option go_package = "krynetic.com/protos/grpc";
option csharp_namespace = "Krynetic.Database.Servers.GRPC.Generated";

package krynetic;

service KryneticRPC {
  rpc Get (Key) returns (Value);
  rpc Set (Entry) returns (Change);

  rpc Subscribe (Key) returns (stream Value);
}

message Key {
  string key = 1;

  oneof has_depth {
    int32 depth = 2;
  }
}

message Value {
  string value = 1;
}

message Entry {
  string key = 1;
  string value = 2;
}

message Change {
  ChangeValue Change = 1;
}

enum ChangeValue {
  NONE = 0;
  ADD = 1;
  REMOVE = 2;
  EDIT = 3;
  ENTER = 4;
  EXIT = 5;
}
```

## Methods

| Method | Request | Response | Description |
|---|---|---|---|
| `Get` | `Key` | `Value` | Returns the value at `key`. When `depth` is set it limits the serialization depth of a subtree. |
| `Set` | `Entry` | `Change` | Writes `value` to `key` and returns what changed (`NONE`, `ADD`, `REMOVE`, `EDIT`, `ENTER`, `EXIT`; see [Change types](../../Concepts/Change-Types.md)). |
| `Subscribe` | `Key` | stream of `Value` | Streams a message every time the value at `key`, or something beneath it, changes. |

Values travel as strings. Structured values come back as text, so parse them in your client.

## C#

```bash
dotnet add package Grpc.Net.Client
dotnet add package Google.Protobuf
dotnet add package Grpc.Tools
```

```xml
<ItemGroup>
  <Protobuf Include="krynetic.proto" GrpcServices="Client" />
</ItemGroup>
```

```csharp
using Grpc.Net.Client;
using Krynetic.Database.Servers.GRPC.Generated;

using var channel = GrpcChannel.ForAddress("http://localhost:50051");
var client = new KryneticRPC.KryneticRPCClient(channel);

var change = await client.SetAsync(new Entry { Key = "/blog/title", Value = "My blog" });
Console.WriteLine(change.Change_);   // ADD, EDIT or NONE

var value = await client.GetAsync(new Key { Key_ = "/blog/title" });
Console.WriteLine(value.Value);

using var call = client.Subscribe(new Key { Key_ = "/blog" });
await foreach (var update in call.ResponseStream.ReadAllAsync())
    Console.WriteLine(update.Value);
```

The generated property names depend on your tooling. A field that has the same name as its message gets a trailing underscore in C# (`Key_`, `Change_`).

## Go

```bash
protoc --go_out=. --go-grpc_out=. krynetic.proto
```

```go
conn, _ := grpc.Dial("localhost:50051", grpc.WithTransportCredentials(insecure.NewCredentials()))
defer conn.Close()
c := pb.NewKryneticRPCClient(conn)

_, _ = c.Set(ctx, &pb.Entry{Key: "/blog/title", Value: "My blog"})
v, _ := c.Get(ctx, &pb.Key{Key: "/blog/title"})
fmt.Println(v.Value)
```

## Python

```bash
pip install grpcio grpcio-tools
python -m grpc_tools.protoc -I. --python_out=. --grpc_python_out=. krynetic.proto
```

```python
import grpc, krynetic_pb2, krynetic_pb2_grpc

with grpc.insecure_channel("localhost:50051") as ch:
    stub = krynetic_pb2_grpc.KryneticRPCStub(ch)
    stub.Set(krynetic_pb2.Entry(key="/blog/title", value="My blog"))
    print(stub.Get(krynetic_pb2.Key(key="/blog/title")).value)
    for update in stub.Subscribe(krynetic_pb2.Key(key="/blog")):
        print(update.value)
```

## grpcurl

Use the proto file, because server reflection may not be available:

```bash
grpcurl -plaintext -proto krynetic.proto -d '{"key":"/blog/title"}' \
  localhost:50051 krynetic.KryneticRPC/Get

grpcurl -plaintext -proto krynetic.proto -d '{"key":"/blog/title","value":"My blog"}' \
  localhost:50051 krynetic.KryneticRPC/Set
```

## Notes

- The server speaks HTTP/2 without TLS. Terminate TLS in a proxy or service mesh for production traffic. See [Security](../../Guides/Security.md).
- Subscriptions are streams tied to the call. Cancel the call to stop.
