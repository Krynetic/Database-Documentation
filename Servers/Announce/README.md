# Announce

**Server name:** `Announce` · **Port:** none

The announce server always starts last, because it depends on the other servers being started first. Start it together with the servers you want it to cover:

```bash
Krynetic.Database --server GraphQL --server MQTT --server Announce
```

Run `Krynetic.Database --help` for details of what it publishes in your build.
