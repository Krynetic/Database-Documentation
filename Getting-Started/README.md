# Getting Started

This page takes you from nothing to a running Krynetic instance that you can read from and write to.

## 1. Start a server

The fastest way is Docker (see [Docker](Docker.md) for persistent storage):

```bash
docker run --rm -it -p 8085:8085 ghcr.io/krynetic/database-releases:latest
```

This starts the [GraphQL server](../Servers/GraphQL/README.md) on port `8085`. Without a storage volume, data lives only as long as the container.

## 2. Write a value

Open <http://localhost:8085> for the built-in GraphiQL page, or use `curl`:

```bash
curl -s http://localhost:8085/graphql \
  -H "Content-Type: application/json" \
  -d '{"query":"mutation { set(key: \"/blog/title\", value: \"My blog\") }"}'
```

## 3. Read it back

```bash
curl -s http://localhost:8085/graphql \
  -H "Content-Type: application/json" \
  -d '{"query":"query { get(key: \"/blog\") }"}'
```

```json
{ "data": { "get": { "title": "My blog" } } }
```

## 4. Listen for changes

In GraphiQL, run:

```graphql
subscription {
  subscribe(key: "/blog") {
    path
    value
  }
}
```

Write to `/blog/title` again from another tab and the subscription receives the change.

## 5. Add another protocol

Servers share one data store. Start MQTT next to GraphQL and watch the same data from an MQTT client:

```bash
docker run --rm -it -p 8085:8085 -p 1883:1883 \
  ghcr.io/krynetic/database-releases:latest \
  --server GraphQL --server MQTT
```

```bash
mosquitto_sub -h localhost -p 1883 -t '/blog/title' -v
```

## Next steps

- [Keep your data between restarts](Configuration.md)
- [Docker](Docker.md), [Docker Compose](Docker-Compose.md) and [Kubernetes](Kubernetes.md) deployments
- [Concepts](../Concepts/README.md): paths, values, subscriptions
- [All servers](../Servers/README.md)
