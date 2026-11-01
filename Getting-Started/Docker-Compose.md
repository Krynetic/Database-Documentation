# Docker Compose

## Community edition

```yaml
# docker-compose.yml
services:
  database:
    image: ghcr.io/krynetic/database-releases:latest
    command: ["--server", "graphql"]
    volumes:
      - ./data:/data
    environment:
      - STORAGE_DIRECTORY=/data
    ports:
      - "8085:8085"
```

## Licensed edition

```yaml
# docker-compose.yml
services:
  database:
    image: ghcr.io/krynetic/database-releases:latest
    command: ["--server", "graphql"]
    volumes:
      - ./data:/data
      - ./license.key:/license.key
    environment:
      - LICENSE_FILE=/license.key
      - STORAGE_DIRECTORY=/data
    ports:
      - "8085:8085"
```

## Several protocols with custom ports

```yaml
services:
  database:
    image: ghcr.io/krynetic/database-releases:latest
    command:
      - "--server"
      - "GraphQL:8085"
      - "--server"
      - "MQTT:1883"
      - "--server"
      - "GRPC:50051"
    volumes:
      - ./data:/data
    environment:
      - STORAGE_DIRECTORY=/data
    ports:
      - "8085:8085"
      - "1883:1883"
      - "50051:50051"
```

## With health checks

Add the [Kubernetes probe server](../Servers/KubernetesProbe/README.md) and use it for the container health check:

```yaml
services:
  database:
    image: ghcr.io/krynetic/database-releases:latest
    command: ["--server", "graphql", "--server", "KubernetesProbe"]
    environment:
      - STORAGE_DIRECTORY=/data
    volumes:
      - ./data:/data
    ports:
      - "8085:8085"
```

## Application next to the database

```yaml
services:
  database:
    image: ghcr.io/krynetic/database-releases:latest
    command: ["--server", "graphql"]
    environment:
      - STORAGE_DIRECTORY=/data
    volumes:
      - db-data:/data

  app:
    image: my-company/my-app:1.0
    environment:
      - KRYNETIC_URL=http://database:8085/graphql
    depends_on:
      - database
    ports:
      - "3000:3000"

volumes:
  db-data:
```

Inside the Compose network the application reaches the database at `http://database:8085`; only the application needs a published port.
