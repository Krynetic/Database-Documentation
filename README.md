# Krynetic Database Documentation

Krynetic Database is a hierarchical, path-addressed data platform that exposes one shared data store through many network protocols at the same time. A value written through one protocol (for example GraphQL) is immediately readable and observable through every other protocol you have enabled (for example MQTT, gRPC, Socket.IO or SPARQL).

Releases and container images: <https://github.com/Krynetic/Database-Releases>

## Where to start

| I want to… | Read |
|---|---|
| Run Krynetic for the first time | [Getting Started](Getting-Started/README.md) |
| Understand paths, values and subscriptions | [Concepts](Concepts/README.md) |
| See every command-line option | [Command line](Commandline.md) |
| Pick and use a protocol server | [Servers](Servers/README.md) |
| Modify values on the server (increment, toggle, append…) | [Operations](Operations.md) |
| Write expressions and computed values | [Expression syntax](Syntax/README.md) |
| Look up a function | [Using functions](Guides/Using-Functions.md) and the [function reference](Functions/README.md) |
| Run jobs on a schedule | [Handlers](Handlers/README.md) and [Schedule](Handlers/Schedule.md) |
| Back up and restore data | [Backup and restore](Guides/Backup-and-Restore.md) |
| Monitor a running instance | [Observability](Guides/Observability.md) |
| Secure a deployment | [Security](Guides/Security.md) |
| Copy a worked example | [Recipes](Guides/Recipes.md) |
| Fix an error | [Troubleshooting](Guides/Troubleshooting.md) |
| Look up ports, server names, terms | [Reference](Reference/README.md) |

## Contents

```text
README.md
Commandline.md                 Command-line reference
Operations.md                  Server-side operations (_op)
Benchmarks.md                  Benchmarks

Getting-Started/
  README.md                    Quick start
  Docker.md
  Docker-Compose.md
  Kubernetes.md
  Configuration.md             Environment variables and storage

Concepts/
  README.md                    Paths, nodes and values
  Data-Types.md                Types and typed string encoding
  Change-Types.md
  Subscriptions.md
  Computed-Values.md

Syntax/
  README.md                    Expression syntax

Servers/
  README.md                    Overview, selection, ports, settings
  GraphQL/
  GRPC/
  SocketIO/
  MQTT/
  WCF/
  Sparql/
  MongoDB/
  SQL/
  Redis/
  S3/
  Couchbase/
  CouchDB/
  AMQP/
  FTP/
  SSH/
  OData/
  HTTP/
  OIDC/
  VirtualDisk/
  KubernetesProbe/
  Announce/

Handlers/
  README.md                    Handlers and the @ namespaces
  Schedule.md                  Scheduler

Functions/                     Function reference (one page per category)

Guides/
  Using-Functions.md
  Backup-and-Restore.md
  Observability.md
  Security.md
  Recipes.md
  Troubleshooting.md

Reference/
  README.md                    Ports, server names, glossary
```
