# Subscriptions

A subscription is a standing request to be told when a path changes. Every protocol offers one in its own native style:

| Protocol | How to subscribe |
|---|---|
| [GraphQL](../Servers/GraphQL/README.md) | `subscription { subscribe(key: "/path") { path value } }` over WebSocket |
| [gRPC](../Servers/GRPC/README.md) | `rpc Subscribe (Key) returns (stream Value)` |
| [Socket.IO](../Servers/SocketIO/README.md) | `socket.emit("subscribe", path)` |
| [MQTT](../Servers/MQTT/README.md) | Subscribe to the topic, or `#` for everything |

## When a subscription fires

A subscription on a path is notified when:

- the value at that path changes,
- a **descendant** of the path changes (subscribing to `/blog` fires for `/blog/title`), or
- an **ancestor** of the path is changed or replaced.

A write that changes nothing (change type `None`) notifies nobody.

## Cross-protocol delivery

Subscriptions are independent of the protocol that made the change. A write over MQTT notifies a GraphQL subscription, and a GraphQL mutation notifies an MQTT subscriber.

## Subscribing to computed values and schedules

[Computed values](Computed-Values.md) can be subscribed to like stored values. Combined with [`@Schedule`](../Handlers/Schedule.md) they produce a stream of timed updates:

```text
subscribe /blog/title
- "Welcome to my blog, time is 2026-10-27 20:00:00 +00:00"
- "Welcome to my blog, time is 2026-10-27 20:00:15 +00:00"
- "Welcome to my blog, time is 2026-10-27 20:00:30 +00:00"
```

## Best practices

- Subscribe to the narrowest path you need. A subscription on `/` receives every change in the store.
- Close subscriptions you no longer need (`complete` in GraphQL, `unsubscribe` in Socket.IO, cancel the stream in gRPC).
- Each subscription is tied to its connection and ends when the connection closes.
