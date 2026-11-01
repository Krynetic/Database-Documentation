# Redis

**Default port:** `6380` · **Server name:** `Redis`

Connect Redis clients to the store. The default port is `6380`, deliberately not Redis's usual `6379`, so the server can run next to a real Redis.

## Start

```bash
Krynetic.Database --server Redis
Krynetic.Database --server Redis:<port>
```

## Connect

```bash
redis-cli -p 6380
```

## Notes

- Use a standard client for the protocol; no Krynetic-specific library is needed.
- Data you write through this server is stored in the shared path tree and is visible through every other [server](../README.md). See [Concepts](../../Concepts/README.md).
- Run `Krynetic.Database --help` for the capabilities and settings of your build, and test the commands your application uses before going to production.
- Protect the port with network controls. See [Security](../../Guides/Security.md).
