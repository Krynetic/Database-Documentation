# Troubleshooting

## Command-line errors

| Message | Cause | Fix |
|---|---|---|
| `At least one server type must be specified.` | `--server` has no valid value | Add a server, for example `--server GraphQL` |
| `Invalid server endpoint: '<value>'.` | A `name:port` pair is malformed or the port is outside 1–65535 | Use `Name:port` with a valid port |
| `Port '<n>' must follow a server type.` | A port number is not preceded by a server name | Write `--server GraphQL 8085` or `--server GraphQL:8085` |
| `Invalid server type or port: '<value>'.` | Unknown server name | See [Command line](../Commandline.md#selecting-servers-and-ports) |
| `Invalid arity detected, should be key and value` | `--server-config` does not have a multiple of three tokens | Give `server key value` for each setting |
| `Invalid server type '<name>'` | Wrong server name in `--server-config` | Use a valid server name |
| `Invalid server configuration key '<key>' for server '<server>'` | The server has no such key | Run `--help` to list supported keys |
| `Invalid value <v>, as it did not parse by any built in parser` | The value could not be typed | Use the [`@enc:`](../Concepts/Data-Types.md#typed-string-encoding) form |
| `Failed to parse loglevel '<v>'` | Unknown log level | Use a level from [Observability](Observability.md#logging) |
| `Cannot import file because it does not exist: '<path>'` | Wrong import path | Check the path, inside the container if you use Docker |

## Connectivity

| Symptom | Likely cause | Fix |
|---|---|---|
| Connection refused | Server not started, or on another port | Check the startup log lines and your `--server Name:port` |
| Works in the container, not outside | Port not published, or bound to loopback | Publish the port (`-p`) and set `HOST=*` in containers and pods |
| Port already in use | Another process uses it | Pick another port with `--server Name:port` |
| Cannot bind port 22 or another privileged port | Missing privileges | Use a port above 1024, for example `SSH:2222` |
| Browser requests blocked | CORS | Set the GraphQL CORS origin; use a proxy for other HTTP servers |

## GraphQL

| Symptom | Cause | Fix |
|---|---|---|
| WebSocket rejected with `Subprotocol required: <name>` | The client did not offer the configured sub-protocol | Request that exact sub-protocol |
| `connection_init received more than once` | Sent twice | Send it once per connection |
| `Connection has not been initialized.` | `subscribe` before `connection_ack` | Wait for `connection_ack` |
| `A subscription already exists for this id` | Duplicate subscription id | Use a unique id per subscription |
| `Subscription is missing its id.` | `subscribe` without `id` | Add an `id` |
| `Missing GraphQL query.` | No `query` field | Send `{"query": "…"}` |
| `Request body must be a JSON object.` | Body is not a JSON object | Send valid JSON |

## Health probes

| Symptom | Cause | Fix |
|---|---|---|
| `/health/ready` or `/health/live` returns `503` | The store did not answer within one second | Check disk latency and CPU limits, raise probe thresholds |
| Pod restarts in a loop | Liveness fails during a slow start | Add a `startupProbe` and raise `failureThreshold` |

## Data

| Symptom | Cause | Fix |
|---|---|---|
| A write reports `None` | The new value equals the stored value | Expected; nobody is notified |
| A computed value does not update | A name in the expression refers to a different node | Use `Lookup("/absolute/path")` |
| A schedule never runs | Invalid `Expression`, or `Content` is not an object | Look for `Invalid schedule expression` in the log; make `Content` an object |
| Data is gone after a container restart | No persistent volume | Mount a volume and set `STORAGE_DIRECTORY` |
| Two instances conflict | The same volume is mounted twice | Run one instance per storage directory |
| `Failed to evaluate '<expression>' due to …` | The expression is invalid | Fix it. See [Expression syntax](../Syntax/README.md) |
