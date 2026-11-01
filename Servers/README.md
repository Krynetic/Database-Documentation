# Servers

Each server is a protocol interface to the same data store. Start the ones you need with `--server`:

```bash
Krynetic.Database --server GraphQL --server MQTT:1883 --server GRPC
```

See [Command line](../Commandline.md#selecting-servers-and-ports) for the syntax and [Reference](../Reference/README.md#default-ports) for default ports.

## Choosing a server

| Need | Use |
|---|---|
| Web and mobile back-ends with live updates | [GraphQL](GraphQL/README.md) |
| Typed service-to-service calls | [gRPC](GRPC/README.md) |
| Event-style web clients | [Socket.IO](SocketIO/README.md) |
| Devices and telemetry | [MQTT](MQTT/README.md) |
| Enterprise integration | [WCF / SOAP](WCF/README.md), [OData](OData/README.md) |
| Linked-data tooling | [SPARQL](Sparql/README.md) |
| Existing database tooling | [MongoDB](MongoDB/README.md), [SQL](SQL/README.md), [Redis](Redis/README.md), [CouchDB](CouchDB/README.md), [Couchbase](Couchbase/README.md) |
| Messaging and streaming | [AMQP](AMQP/README.md) |
| Files | [S3](S3/README.md), [FTP](FTP/README.md), [SSH / SFTP](SSH/README.md), [Virtual disk](VirtualDisk/README.md) |
| REST / OpenAPI | [HTTP](HTTP/README.md) |
| Identity | [OIDC](OIDC/README.md) |
| Container health checks | [Kubernetes probe](KubernetesProbe/README.md) |

## Overview

| Server | `--server` name | Default port | Read | Write | Subscribe |
|---|---|---|---|---|---|
| [GraphQL](GraphQL/README.md) | `GraphQL` | 8085 | Yes | Yes | Yes (WebSocket) |
| [gRPC](GRPC/README.md) | `GRPC` | 50051 | Yes | Yes | Yes (stream) |
| [Socket.IO](SocketIO/README.md) | `SocketIO` | 9001 | Yes | Yes | Yes |
| [MQTT](MQTT/README.md) | `MQTT` | 1883 | Yes | Yes | Yes |
| [WCF](WCF/README.md) | `WCF` | 8086 (HTTP), 8090 (TCP) | Yes | Yes | No |
| [SPARQL](Sparql/README.md) | `Sparql` | 3001 | Yes | Planned | No |
| [MongoDB](MongoDB/README.md) | `MongoDB` | 27017 | Yes | Yes | n/a |
| [SQL](SQL/README.md) | `SQL` | 5432 | | | |
| [Redis](Redis/README.md) | `Redis` | 6380 | | | |
| [S3](S3/README.md) | `S3` | 9000 | | | |
| [Couchbase](Couchbase/README.md) | `Couchbase` | 11210 | | | |
| [CouchDB](CouchDB/README.md) | `CouchDB` | 5984 | | | |
| [AMQP](AMQP/README.md) | `AMQP` | 5672 | | | |
| [FTP](FTP/README.md) | `FTP` | 2121 | | | |
| [SSH / SFTP](SSH/README.md) | `SSH`, `SFTP` | 22 | | | |
| [OData](OData/README.md) | `OData` | 8081 | | | |
| [HTTP (OpenAPI)](HTTP/README.md) | `HTTP` | 8080 | | | |
| [OIDC](OIDC/README.md) | `OIDC` | 8250 | | | |
| [Virtual disk](VirtualDisk/README.md) | `VirtualDisk` | mount | | | |
| [Kubernetes probe](KubernetesProbe/README.md) | `KubernetesProbe` | 9999 | health | | |
| [Announce](Announce/README.md) | `Announce` | none | | | |

Empty cells mean the page documents how to start and connect to the server. Run `--help` for the capabilities in your build.

## Shared behaviour

- **One store.** What you write through one server is visible through every other server. See [Concepts](../Concepts/README.md).
- **Plain-text transports.** HTTP-based servers listen without TLS by default. Terminate TLS in front of them. See [Security](../Guides/Security.md).
- **Ports.** Override any port with `--server Name:port`. Publish only the ports of servers you start.
- **Settings.** Server-specific settings use `--server-config`. See [Command line](../Commandline.md#server-specific-settings).
