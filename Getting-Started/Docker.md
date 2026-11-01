# Docker

The image is published at:

```text
ghcr.io/krynetic/database-releases:latest
```

Pin a specific tag for production deployments rather than using `latest`. Releases: <https://github.com/Krynetic/Database-Releases>.

Arguments after the image name are passed to `Krynetic.Database`. See the [command-line reference](../Commandline.md).

## Quick start

```bash
docker run --rm -it -p 8085:8085 ghcr.io/krynetic/database-releases:latest
```

Starts the GraphQL server on port `8085`. Data is lost when the container is removed.

## Persistent storage

```bash
docker run -d --name krynetic \
  -p 8085:8085 \
  -v krynetic-data:/data \
  -e STORAGE_DIRECTORY=/data \
  ghcr.io/krynetic/database-releases:latest \
  --server GraphQL
```

## Several servers in one container

```bash
docker run -d --name krynetic \
  -p 8085:8085 -p 1883:1883 -p 50051:50051 -p 9001:9001 \
  -v krynetic-data:/data \
  -e STORAGE_DIRECTORY=/data \
  ghcr.io/krynetic/database-releases:latest \
  --server GraphQL --server MQTT --server GRPC --server SocketIO
```

Publish only the ports of the servers you start.

## Custom ports

```bash
docker run -d -p 9090:9090 \
  -e STORAGE_DIRECTORY=/data -v krynetic-data:/data \
  ghcr.io/krynetic/database-releases:latest \
  --server GraphQL:9090
```

## Licensed edition

```bash
docker run -d --name krynetic \
  -p 8085:8085 \
  -v krynetic-data:/data \
  -v "$PWD/license.key:/license.key:ro" \
  -e STORAGE_DIRECTORY=/data \
  -e LICENSE_FILE=/license.key \
  ghcr.io/krynetic/database-releases:latest \
  --server GraphQL
```

## Bind only to localhost

Publish ports on the loopback interface to keep a server off the network:

```bash
docker run -d -p 127.0.0.1:8085:8085 ghcr.io/krynetic/database-releases:latest --server GraphQL
```

## Logs

```bash
docker logs -f krynetic
```

## Exposed ports

See [Ports](../Reference/README.md#default-ports) for every server's default port.
