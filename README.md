
# Releases
**[https://github.com/Krynetic/Database-Releases](https://github.com/Krynetic/Database-Releases)**

# Installation

## Docker licensed edition using GraphQL

### Image: ghcr.io/krynetic/database-releases:latest

```ruby
#docker-compose.yml
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
      - HOST=*
    ports:
      - "8085:8085"
      # Add more ports here
```

## Kubernetes Community edition using GraphQL
```ruby
apiVersion: apps/v1
kind: Deployment
metadata:
  name: database
spec:
  replicas: 1
  selector:
    matchLabels:
      app: database
  template:
    metadata:
      labels:
        app: database
    spec:
      containers:
        - name: database
          image: ghcr.io/krynetic/database-releases:latest
          args: ["--server", "graphql"]
          env:
            - name: STORAGE_DIRECTORY
              value: /data
            - name: HOST
              value: "*"
          ports:
            - containerPort: 8085
          volumeMounts:
            - name: data
              mountPath: /data
      volumes:
        - name: data
          persistentVolumeClaim:
            claimName: db-data
---
apiVersion: v1
kind: PersistentVolumeClaim
metadata:
  name: db-data
spec:
  accessModes: [ReadWriteOnce]
  resources:
    requests:
      storage: 5Gi
---
apiVersion: v1
kind: Service
metadata:
  name: database
spec:
  selector:
    app: database
  ports:
    - name: http
      port: 8085
      targetPort: 8085
      protocol: TCP
```

## Kubernetes licensed edition using GraphQL
```ruby
apiVersion: apps/v1
kind: Deployment
metadata:
  name: database
spec:
  replicas: 1
  selector:
    matchLabels:
      app: database
  template:
    metadata:
      labels:
        app: database
    spec:
      containers:
        - name: database
          image: ghcr.io/krynetic/database-releases:latest
          args: ["--server", "graphql"]
          env:
            - name: LICENSE_FILE
              value: /license.key
            - name: STORAGE_DIRECTORY
              value: /data
            - name: HOST
              value: "*"
          ports:
            - containerPort: 8085
          volumeMounts:
            - name: data
              mountPath: /data
            - name: license
              mountPath: /license.key
              subPath: license.key
      volumes:
        - name: data
          persistentVolumeClaim:
            claimName: db-data
        - name: license
          configMap:
            name: db-license
---
apiVersion: v1
kind: ConfigMap
metadata:
  name: db-license
data:
  license.key: |
    # paste license content here
---
apiVersion: v1
kind: PersistentVolumeClaim
metadata:
  name: db-data
spec:
  accessModes: [ReadWriteOnce]
  resources:
    requests:
      storage: 5Gi
---
apiVersion: v1
kind: Service
metadata:
  name: database
spec:
  selector:
    app: database
  ports:
    - name: http
      port: 8085
      targetPort: 8085
      protocol: TCP
```
### Exported docker ports

```dockerfile
EXPOSE port/protocol
```

| Service   | Port     |
|-----------|----------|
| Redis     | 6380/tcp |
| MQTT      | 1883/tcp |
| S3        | 9000/tcp |
| MongoDB   | 27017/tcp|
| Kafka     | 9092/tcp |
| Couchbase | 11210/tcp|
| CouchDB   | 5984/tcp |
| SQL       | 5432/tcp |
| FTP       | 2121/tcp |
| SSH       | 22/tcp   |
| WCF TCP   | 8090/tcp |
| WCF HTTP  | 8086/tcp |
| GraphQL   | 8085/tcp |
| OpenAPI   | 8080/tcp |
| OData     | 8081/tcp |
| GRPC      | 50051/tcp|

## Star History

[![Star History Chart](https://api.star-history.com/svg?repos=Krynetic/Database-Documentation,Krynetic/Database-Releases&type=date&legend=top-left)](https://www.star-history.com/#Krynetic/Database-Documentation&Krynetic/Database-Releases&type=date&legend=top-left)
