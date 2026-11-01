# MQTT

**Default endpoint:** `mqtt://localhost:1883` · **Server name:** `MQTT`

```bash
Krynetic.Database --server MQTT
```

## Topics and paths

MQTT topics map onto store paths: the topic `/blog/title` addresses the path `/blog/title`. The wildcard topic `#` covers the whole store.

## Connect

| Setting | Value |
|---|---|
| Protocol | `mqtt://` |
| Host | `localhost` |
| Port | `1883` |

## Command-line clients (Mosquitto)

```bash
# Subscribe to everything
mosquitto_sub -h localhost -p 1883 -t '#' -v

# Subscribe to one path
mosquitto_sub -h localhost -p 1883 -t '/blog/title' -v

# Publish a value
mosquitto_pub -h localhost -p 1883 -t '/blog/title' -m 'Hello from MQTT'
```

The store is shared, so a value published over MQTT is readable through GraphQL, gRPC and every other enabled server, and changes made through those servers reach MQTT subscribers.

## JavaScript

```javascript
import mqtt from "mqtt";

const client = mqtt.connect("mqtt://localhost:1883");

client.on("connect", () => {
  client.subscribe("/blog/title");
  client.publish("/blog/title", "Hello from Node");
});

client.on("message", (topic, payload) => {
  console.log(topic, payload.toString());
});
```

## Supported clients

Any standards-compliant MQTT client works. [MQTT Explorer](https://mqtt-explorer.com) ([source](https://github.com/thomasnordquist/MQTT-Explorer)) is a convenient graphical client:

1. Create a new connection with protocol `mqtt://`, host `localhost`, port `1883`.
2. Connect. The topic tree mirrors the path tree.
3. Subscribe to `#` or to a topic such as `/blog/title`.
