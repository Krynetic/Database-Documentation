# Recipes

Worked examples that combine servers, operations, expressions and schedules.

## Device telemetry to a live dashboard

Start MQTT for devices and GraphQL for the dashboard:

```bash
Krynetic.Database --storage-directory ./data --server MQTT --server GraphQL
```

A device publishes a reading:

```bash
mosquitto_pub -h localhost -p 1883 -t '/sensors/room1/temperature' -m '21.5'
```

The dashboard subscribes through GraphQL:

```graphql
subscription {
  subscribe(key: "/sensors") {
    path
    value
  }
}
```

Each reading arrives as it is written, and a `get` of `/sensors` returns the latest values for all rooms.

## A shared counter

```graphql
mutation {
  set(key: "/stats/visits", value: { _op: "increment", value: 1 })
}
```

The increment runs in the server, so concurrent callers through any protocol never lose updates. See [Operations](../Operations.md).

## A value that refreshes itself

Combine a [schedule](../Handlers/Schedule.md) with a computed value:

```graphql
mutation Schedule($value: JSON) {
  set(key: "/@Schedule/clock", value: $value)
}
```

```json
{
  "value": {
    "Expression": "1s",
    "Target": "/clock",
    "Content": { "now.expression": "now()" }
  }
}
```

Clients on any protocol that subscribe to `/clock/now` receive one update per second.

## A derived total

```graphql
mutation {
  set(key: "/order", value: { price: 9.5, quantity: 4 })
  set(key: "/order/total.expression", value: "price * quantity")
}
```

`get(key: "/order/total")` returns `38`. Changing `/order/quantity` recalculates `total` and notifies its subscribers. See [Computed values](../Concepts/Computed-Values.md).

## Browse the same data as linked data

Start `--server GraphQL --server Sparql`. Whatever GraphQL writes appears as triples in [SPARQL](../Servers/Sparql/README.md), each path an IRI under `http://krynetic.com/`.

## Append to a log

```graphql
mutation {
  set(key: "/log", value: { _op: "appendline", value: "deploy finished" })
}
```

Each call adds one line to the `/log` value.

## Toggle a feature flag

```graphql
mutation {
  set(key: "/flags/new-ui", value: { _op: "toggle" })
}
```

Subscribers to `/flags` learn about the change at once.
