# SQL

**Default port:** `5432` · **Server name:** `SQL`

Connect SQL client tools and drivers to the store.

## Start

```bash
Krynetic.Database --server SQL
Krynetic.Database --server SQL:<port>
```

## Connect

```bash
psql -h localhost -p 5432
```

Use the host `localhost` and the configured port in any SQL client or driver.

## Settings

| Key | Type | Default | Description |
|---|---|---|---|
| `maxmessagebody` | integer | `1000000` | Largest accepted protocol message body in bytes. Raise it if clients send large statements or parameters. |

```bash
Krynetic.Database --server SQL --server-config SQL maxmessagebody 5000000
```

## Notes

- Use a standard client for the protocol; no Krynetic-specific library is needed.
- Data you write through this server is stored in the shared path tree and is visible through every other [server](../README.md). See [Concepts](../../Concepts/README.md).
- Run `Krynetic.Database --help` for the capabilities and settings of your build, and test the commands your application uses before going to production.
- Protect the port with network controls. See [Security](../../Guides/Security.md).
