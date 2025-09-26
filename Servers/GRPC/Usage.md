# Krynetic gRPC (Google RPC)

### `Default Endpoint` 
#### [http://localhost:50051](http://localhost:50051)

### `Protobuf` Contract

```ruby
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