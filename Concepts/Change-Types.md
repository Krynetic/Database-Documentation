# Change types

Every write reports what it did to the store. Protocols that return a result to the writer (Socket.IO `set`, gRPC `Set`) return one of these values.

| Value | Meaning |
|---|---|
| `None` | The write changed nothing: the new value equals the existing value |
| `Add` | A new path was created |
| `Remove` | A path was removed |
| `Edit` | An existing value was replaced |
| `Enter` | A subscription scope was entered |
| `Exit` | A subscription scope was left |

Writing a value that equals the stored one is reported as `None` and does not notify subscribers.

In gRPC the values are the enum `NONE`, `ADD`, `REMOVE`, `EDIT`, `ENTER`, `EXIT`. In Socket.IO they are returned as the strings `None`, `Add`, `Remove`, `Edit`, `Enter`, `Exit`.
