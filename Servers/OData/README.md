# OData

**Default port:** `8081` · **Server name:** `OData`

Connect OData clients to the store.

## Start

```bash
Krynetic.Database --server OData
Krynetic.Database --server OData:<port>
```

## Connect

Use `http://localhost:8081` as the service root.

## Notes

- Use a standard client for the protocol; no Krynetic-specific library is needed.
- Data you write through this server is stored in the shared path tree and is visible through every other [server](../README.md). See [Concepts](../../Concepts/README.md).
- Run `Krynetic.Database --help` for the capabilities and settings of your build, and test the commands your application uses before going to production.
- Protect the port with network controls. See [Security](../../Guides/Security.md).
