# Krynetic Socket.IO

### `Default Endpoint` 
#### [http://localhost:9001](http://localhost:9001)

## Events

## `get`
Retrieve a value at a given path.  

**Event:** `get`  
**Request:**
`string` path

**Response**:
`JSON`

## `set`
Retrieve a value at a given path.  

**Event:** `set`  
**Request:**
`string` path

**Response**:
`ChangeType (string)`
None, Add, Remove, Edit, Enter, Exit)

## `subscribe`
Retrieve a value at a given path.  

**Event:** `subscribe`  
**Request:**
`string` path

**Response**:
`Streaming JSON`

## `unsubscribe`
Retrieve a value at a given path.  

**Event:** `unsubscribe`  
**Request:**
`string` path

**Response**:
`int` (removed subscription counts)

# Example

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