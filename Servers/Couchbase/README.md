# Couchbase

**Default port:** `11210` · **Server name:** `Couchbase`

Connect Couchbase SDKs to the store.

## Start

```bash
Krynetic.Database --server Couchbase
Krynetic.Database --server Couchbase:<port>
```

## Connect

Point the SDK at `localhost` (data service port `11210`).

## Notes

- Use a standard client for the protocol; no Krynetic-specific library is needed.
- Data you write through this server is stored in the shared path tree and is visible through every other [server](../README.md). See [Concepts](../../Concepts/README.md).
- Run `Krynetic.Database --help` for the capabilities and settings of your build, and test the commands your application uses before going to production.
- Protect the port with network controls. See [Security](../../Guides/Security.md).
