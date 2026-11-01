# Concepts

## One store, many protocols

A running Krynetic instance owns exactly one data store. Every server you start (`--server GraphQL`, `--server MQTT`, …) is a protocol interface to that store. Interfaces do not keep their own copies of the data, which has three practical consequences:

- **Consistency.** A write through any protocol is visible through every other protocol as soon as it completes.
- **Cross-protocol notifications.** A change made through one protocol triggers [subscriptions](Subscriptions.md) made through another. A GraphQL mutation can wake up an MQTT subscriber, a Socket.IO client and a gRPC stream at the same time.
- **Choose protocols per deployment.** Start only the interfaces you need. Every interface you do not start is a port you do not have to secure.

## Paths

All data is addressed by a **path**, written like a file-system path.

| Path | Meaning |
|---|---|
| `/` | The root of the store |
| `/blog` | A node called `blog` directly under the root |
| `/blog/title` | A value called `title` inside the `blog` node |
| `/users/0/name` | The `name` value of the first element of `users` |

Rules:

- Paths use `/` as separator.
- Reading a path returns the value at that path. If the path is a node, the whole subtree is returned.
- Writing to a path whose parent nodes do not exist creates the missing parents.
- Names that begin with `@` are reserved for [handlers](../Handlers/README.md).
- Each protocol maps its own addressing onto paths: GraphQL uses the `key` argument, MQTT uses the topic, SPARQL uses subject IRIs. Each [server page](../Servers/README.md) shows the mapping.

## Nodes and values

The store is a tree. A **node** (also called a dictionary or directory) contains named children. A **value** is a leaf.

```json
{
  "blog": {
    "title": "My blog",
    "data": { "one": 1, "two": "2", "three": 3.0 }
  },
  "users": [
    { "name": "admin" },
    { "name": "guest" }
  ]
}
```

Lists are stored as nodes whose children are named `0`, `1`, `2`, …, so `/users/1/name` addresses `guest` in the example above.

Writing an object to a path merges its children into the existing node and creates the ones that do not exist yet. Writing a single value replaces the value.

## Types

Values are typed. See [Data types](Data-Types.md) for the list and for the `@enc:` text encoding that lets text-only protocols carry typed values.

## What a write tells you

Every write reports what it did: `None`, `Add`, `Remove`, `Edit`, `Enter` or `Exit`. See [Change types](Change-Types.md).

## Listening for changes

Any client can subscribe to a path. See [Subscriptions](Subscriptions.md).

## Values that compute themselves

A property whose name ends in `.expression` is calculated by the engine. See [Computed values](Computed-Values.md) and [Expression syntax](../Syntax/README.md).

## Modifying values on the server

Send an object with `_op` to increment, toggle, append and more, without a read-modify-write cycle in the client. See [Operations](../Operations.md).

## Work that runs for you

Resources under `@` paths, such as [`@Schedule`](../Handlers/Schedule.md), are run by the engine. See [Handlers](../Handlers/README.md).
