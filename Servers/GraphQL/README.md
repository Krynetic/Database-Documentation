# GraphQL

**Default endpoint:** <http://localhost:8085> · **Server name:** `GraphQL`

```bash
Krynetic.Database --server GraphQL
Krynetic.Database --server GraphQL:9090
```

## Endpoints

| Method | Path | Purpose |
|---|---|---|
| `GET` | `/` | Interactive GraphiQL page in the browser |
| `POST` | `/graphql` | Queries and mutations |
| `OPTIONS` | `/graphql` | CORS preflight; answers `204 No Content` with CORS headers |
| `GET` | `/graphql` (WebSocket upgrade) | Subscriptions |

## Schema

| Root | Field | Arguments | Returns |
|---|---|---|---|
| `query` | `get` | `key` (path) | The JSON value at the path (a whole subtree for a node) |
| `mutation` | `set` | `key` (path), `value` (any JSON value or an [operation](../../Operations.md)) | The result of the write |
| `subscription` | `subscribe` | `key` (path) | A stream of changes with the fields `path` and `value` |

The GraphiQL page at `/` shows the exact schema of your build in its documentation explorer.

## get

Get data at a certain path.

```graphql
query {
  get(key: "/")
}
```

```json
{
  "blog": {
    "title": "My blog",
    "data": { "one": 1, "two": "2", "three": 3 }
  }
}
```

A single value:

```graphql
query {
  get(key: "/blog/title")
}
```

## set

Set data at a certain path.

```graphql
mutation {
  set(key: "/", value: {
    blog: {
      title: "My blog",
      data: {
        one: 1,
        two: "2",
        three: 3.0
      }
    }
  })
}
```

Writing an object merges its children into the existing tree. A single value:

```graphql
mutation {
  set(key: "/blog/title", value: "My new blog")
}
```

Several writes in one request:

```graphql
mutation {
  set(key: "/str1", value: "Hello")
  set(key: "/bool1", value: false)
  set(key: "/number1", value: 1)
}
```

To modify a value instead of replacing it, pass an [operation](../../Operations.md):

```graphql
mutation {
  set(key: "/number1", value: { _op: "increment", value: 3 })
}
```

## subscribe

Continuously listen for changes at a path (and below it).

```graphql
subscription {
  subscribe(key: "/") {
    path
    value
  }
}
```

```json
{
  "path": "blog/title",
  "value": "My blog"
}
```

## Variables

```graphql
mutation Update($key: String!, $value: JSON) {
  set(key: $key, value: $value)
}
```

```json
{
  "query": "mutation Update($key: String!, $value: JSON) { set(key: $key, value: $value) }",
  "operationName": "Update",
  "variables": { "key": "/blog/title", "value": "Hello from variables" }
}
```

`variables` must be a JSON object. Whole numbers are written as 64-bit integers and other numbers as decimals. Use variables when a key or field name is not a valid GraphQL name, for example `title.expression`.

## Calling over HTTP

```bash
curl -s http://localhost:8085/graphql \
  -H "Content-Type: application/json" \
  -d '{"query":"query { get(key: \"/\") }"}'
```

JavaScript:

```javascript
const res = await fetch("http://localhost:8085/graphql", {
  method: "POST",
  headers: { "Content-Type": "application/json" },
  body: JSON.stringify({
    query: `mutation($k: String!, $v: JSON) { set(key: $k, value: $v) }`,
    variables: { k: "/blog/title", v: "My blog" }
  })
});
console.log(await res.json());
```

Python:

```python
import requests

r = requests.post(
    "http://localhost:8085/graphql",
    json={"query": 'query { get(key: "/blog") }'},
)
print(r.json())
```

C#:

```csharp
using var http = new HttpClient { BaseAddress = new Uri("http://localhost:8085") };
var response = await http.PostAsJsonAsync("/graphql", new
{
    query = "query { get(key: \"/blog/title\") }"
});
Console.WriteLine(await response.Content.ReadAsStringAsync());
```

## Subscriptions over WebSocket

Open a WebSocket to `/graphql` and offer the sub-protocol configured in the `transport` [setting](#settings). If the client does not offer it, the server answers `400 Bad Request` with the header `Sec-WebSocket-Protocol: Subprotocol required: <name>`.

Message flow (the `graphql-ws` family of protocols):

1. The client opens the WebSocket.
2. The client sends `{"type":"connection_init"}` **once**. A second one closes the socket with a policy-violation status.
3. The server replies `{"type":"connection_ack"}`.
4. The client sends `{"id":"1","type":"subscribe","payload":{"query":"subscription { subscribe(key: \"/\") { path value } }"}}`. The `id` is required and must be unique among the connection's active subscriptions.
5. The server sends `{"id":"1","type":"next","payload":{…}}` for every change.
6. The client stops with `{"id":"1","type":"complete"}`. The server also sends `complete` when a stream ends.
7. `ping` is answered with `pong`.

Errors arrive as `{"id":"1","type":"error","payload":[{"message":"…"}]}` followed by `complete`. Only text frames are accepted.

Browser client with the `graphql-ws` library:

```javascript
import { createClient } from "graphql-ws";

const client = createClient({ url: "ws://localhost:8085/graphql" });

client.subscribe(
  { query: 'subscription { subscribe(key: "/blog/title") { path value } }' },
  {
    next: (msg) => console.log("change", msg.data),
    error: (err) => console.error(err),
    complete: () => console.log("done"),
  }
);
```

## Errors

| Situation | HTTP status | Body |
|---|---|---|
| Body is not a JSON object | 400 | `{"errors":[{"message":"Request body must be a JSON object."}]}` |
| `query` is missing or empty | 400 | `{"errors":[{"message":"Missing GraphQL query."}]}` |
| Invalid query or a failing field | 200 | Standard GraphQL `errors` array |
| Unexpected server failure | 500 | `{"errors":[{"message":"…"}]}` |

## Settings

The server has settings for the endpoint path, the WebSocket sub-protocol (`transport`) and CORS (allowed origin, methods, headers). Run `--help` for the exact key names and defaults of your build and set them with `--server-config GraphQL <key> <value>`. See [Command line](../../Commandline.md#server-specific-settings).

## CORS

Browsers calling from another origin send an `OPTIONS` preflight. The server answers `204` with `Access-Control-Allow-Origin`, `Access-Control-Allow-Methods` and `Access-Control-Allow-Headers` from the CORS settings. Restrict the allowed origin in production.

## See also

[Operations](../../Operations.md) · [Subscriptions](../../Concepts/Subscriptions.md) · [Troubleshooting](../../Guides/Troubleshooting.md#graphql)
