# Socket.IO

**Default endpoint:** <http://localhost:9001> · **Server name:** `SocketIO`

```bash
Krynetic.Database --server SocketIO
```

Customise the message sent to clients after they connect:

```bash
Krynetic.Database --server SocketIO --server-config SocketIO welcomebanner "Welcome to Krynetic"
```

## Events

| Event | Arguments | Acknowledgement |
|---|---|---|
| `get` | `path` (string) | The value at `path`, as JSON |
| `set` | `path` (string), `value` | The [change type](../../Concepts/Change-Types.md): `None`, `Add`, `Remove`, `Edit`, `Enter` or `Exit` |
| `subscribe` | `path` (string) | Subscribes the connection to changes at `path`; changes stream back as JSON |
| `unsubscribe` | `path` (string) | The number of subscriptions removed |

## Example

```javascript
import { io } from "socket.io-client";

const socket = io("http://localhost:9001");

socket.on("connect", () => {
  console.log("Connected:", socket.id);

  socket.emit("get", "/blog/title", (res) => {
    console.log("GET response:", res);
  });

  socket.emit("set", "/blog/title", "New blog title", (res) => {
    console.log("SET response:", res); // None | Add | Remove | Edit | Enter | Exit
  });

  socket.emit("subscribe", "/blog/title", (res) => {
    console.log("Subscribed response:", res);
  });

  socket.emit("unsubscribe", "/blog/title", (count) => {
    console.log("Unsubscribed count:", count);
  });
});

socket.on("disconnect", () => {
  console.log("Disconnected");
});
```

## Notes

- Subscriptions belong to a connection and end when the client disconnects.
- Browsers on another origin need the server to be reachable from the page, either on the same origin or through a reverse proxy that adds the right CORS headers.
- Serve the server over TLS through a proxy for production. See [Security](../../Guides/Security.md).
