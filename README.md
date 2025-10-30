
# Releases
**[https://github.com/Krynetic/Database-Releases](https://github.com/Krynetic/Database-Releases)**

# Installation

## Docker

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

### Exported docker ports

```dockerfile
#Redis >
EXPOSE 6380/tcp 
#MQTT >
EXPOSE 1883/tcp 
#S3 >
EXPOSE 9000/tcp
#MongoDB >
EXPOSE 27017/tcp
#Kafka >
EXPOSE 9092/tcp 
#Couchbase >
EXPOSE 11210/tcp 
#CouchDB >
EXPOSE 5984/tcp 
#SQL >
EXPOSE 5432/tcp 
#FTP >
EXPOSE 2121/tcp 
#SSH >
EXPOSE 22/tcp 
#WCF TCP >
EXPOSE 8090/tcp 
#WCF HTTP >
EXPOSE 8086/tcp 
#GraphQL >
EXPOSE 8085/tcp 
#OpenAPI >
EXPOSE 8080/tcp 
#OData >
EXPOSE 8081/tcp 
#GRPC >
EXPOSE 50051/tcp
```

## Star History

[![Star History Chart](https://api.star-history.com/svg?repos=Krynetic/Database-Documentation,Krynetic/Database-Releases&type=date&legend=top-left)](https://www.star-history.com/#Krynetic/Database-Documentation&Krynetic/Database-Releases&type=date&legend=top-left)
