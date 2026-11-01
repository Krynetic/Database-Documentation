# Reference

## Default ports

| Server | `--server` name | Default port | Page |
|---|---|---|---|
| Redis | `Redis` | 6380/tcp | [Redis](../Servers/Redis/README.md) |
| MQTT | `MQTT` | 1883/tcp | [MQTT](../Servers/MQTT/README.md) |
| S3 | `S3` | 9000/tcp | [S3](../Servers/S3/README.md) |
| MongoDB | `MongoDB` | 27017/tcp | [MongoDB](../Servers/MongoDB/README.md) |
| Couchbase | `Couchbase` | 11210/tcp | [Couchbase](../Servers/Couchbase/README.md) |
| CouchDB | `CouchDB` | 5984/tcp | [CouchDB](../Servers/CouchDB/README.md) |
| SQL | `SQL` | 5432/tcp | [SQL](../Servers/SQL/README.md) |
| FTP | `FTP` | 2121/tcp | [FTP](../Servers/FTP/README.md) |
| SSH / SFTP | `SSH`, `SFTP` | 22/tcp | [SSH](../Servers/SSH/README.md) |
| WCF (TCP) | `WCF` | 8090/tcp | [WCF](../Servers/WCF/README.md) |
| WCF (HTTP) | `WCF` | 8086/tcp | [WCF](../Servers/WCF/README.md) |
| GraphQL | `GraphQL` | 8085/tcp | [GraphQL](../Servers/GraphQL/README.md) |
| OpenAPI | `HTTP` | 8080/tcp | [HTTP](../Servers/HTTP/README.md) |
| OData | `OData` | 8081/tcp | [OData](../Servers/OData/README.md) |
| gRPC | `GRPC` | 50051/tcp | [gRPC](../Servers/GRPC/README.md) |
| Socket.IO | `SocketIO` | 9001/tcp | [Socket.IO](../Servers/SocketIO/README.md) |
| SPARQL | `Sparql` | 3001/tcp | [SPARQL](../Servers/Sparql/README.md) |
| AMQP | `AMQP` | 5672/tcp | [AMQP](../Servers/AMQP/README.md) |
| OIDC | `OIDC` | 8250/tcp | [OIDC](../Servers/OIDC/README.md) |
| Kubernetes probes | `KubernetesProbe` | 9999/tcp | [Probe](../Servers/KubernetesProbe/README.md) |
| Virtual disk | `VirtualDisk` | none | [Virtual disk](../Servers/VirtualDisk/README.md) |
| Announce | `Announce` | none | [Announce](../Servers/Announce/README.md) |

Override any port with `--server Name:port`.

In Dockerfiles and Compose files the exposed ports are written `EXPOSE port/protocol`, for example `EXPOSE 8085/tcp`.

## Typical clients

| Server | Typical client |
|---|---|
| GraphQL | GraphiQL, Apollo, urql, `graphql-ws` |
| gRPC | gRPC clients, `grpcurl` |
| Socket.IO | `socket.io-client` |
| MQTT | Mosquitto, MQTT Explorer, `mqtt.js` |
| WCF | WCF and SOAP clients |
| SPARQL | SPARQL clients |
| MongoDB | `mongosh`, MongoDB drivers |
| SQL | `psql`, SQL drivers |
| Redis | `redis-cli`, Redis clients |
| S3 | AWS CLI and SDKs |
| CouchDB | CouchDB clients, HTTP |
| AMQP | RabbitMQ / AMQP clients |
| FTP | FTP clients |
| SSH / SFTP | `ssh`, `sftp` |

## Command-line options

See [Command line](../Commandline.md).

## Environment variables

| Variable | Equivalent |
|---|---|
| `STORAGE_DIRECTORY` | `--storage-directory` |
| `LICENSE_FILE` | `--license-file` |
| `HOST` | Bind address (`*` for all interfaces) |

## Operations

`add`, `remove`, `toggle`, `increment`, `decrement`, `multiply`, `divide`, `test`, `append`, `appendline`, `rename`, `expression`. See [Operations](../Operations.md).

## Change types

`None`, `Add`, `Remove`, `Edit`, `Enter`, `Exit`. See [Change types](../Concepts/Change-Types.md).

## Glossary

| Term | Meaning |
|---|---|
| Path | The address of a value or node, such as `/blog/title` |
| Node | A container of named children (also called a directory or dictionary) |
| Value | A leaf holding a typed primitive |
| Computed value | A value defined by a `.expression` property |
| Operation | A server-side modification sent as an object with `_op` |
| Handler | A declarative resource under an `@` path that Krynetic keeps running |
| Subscription | A standing request to be notified when a path changes |
| Change type | The result of a write: `None`, `Add`, `Remove`, `Edit`, `Enter`, `Exit` |
| Store | The one shared data tree behind all servers |
