# MongoDB (experimental)

**Default endpoint:** `mongodb://localhost:27017` · **Server name:** `MongoDB`

```bash
Krynetic.Database --enable-experimental --server MongoDB \
  --server-config MongoDB adminuser admin \
  --server-config MongoDB adminpassword "a-strong-password"
```

At startup the server logs that it is experimental and which administrator user it uses.

## Settings

| Key | Default | Description |
|---|---|---|
| `adminuser` | `admin` | Administrator user name |
| `adminpassword` | `pass` | Administrator password |

**Always set `adminpassword` before exposing this server beyond your own machine.** See [Security](../../Guides/Security.md).

## Protocol support

- Wire protocol messages `OP_MSG` and `OP_QUERY` are supported. Other operation codes return an "Unsupported opCode" error.
- The server advertises feature compatibility version `8.0` and a maximum BSON document size of 16 MiB (16,777,216 bytes).
- It reports a single-member replica set named `rs0`.
- TLS is detected automatically for each connection (TLS 1.2 and 1.3). With TLS the server presents a self-signed certificate and requires a client certificate. Plain connections are accepted on the same port.

## Connect

```bash
mongosh "mongodb://admin:a-strong-password@localhost:27017"
```

Node.js:

```javascript
import { MongoClient } from "mongodb";

const client = new MongoClient("mongodb://admin:a-strong-password@localhost:27017");
await client.connect();
const db = client.db("app");
await db.collection("users").insertOne({ name: "admin" });
console.log(await db.collection("users").find().toArray());
```

C#:

```csharp
var client = new MongoClient("mongodb://admin:a-strong-password@localhost:27017");
var users = client.GetDatabase("app").GetCollection<BsonDocument>("users");
await users.InsertOneAsync(new BsonDocument("name", "admin"));
```

Because this server is experimental, test your driver and the commands your application uses before relying on it in production. Drivers that depend on operation codes outside the supported ones will not work.
