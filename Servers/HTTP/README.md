# HTTP (OpenAPI)

**Default port:** `8080` · **Server name:** `HTTP`

A REST/OpenAPI interface to the store. It is started with the server name `HTTP`.

## Start

```bash
Krynetic.Database --server HTTP
Krynetic.Database --server HTTP:<port>
```

## Connect

Open <http://localhost:8080> in a browser, or use any HTTP or OpenAPI-generated client against it.

## Notes

- Use a standard client for the protocol; no Krynetic-specific library is needed.
- Data you write through this server is stored in the shared path tree and is visible through every other [server](../README.md). See [Concepts](../../Concepts/README.md).
- Run `Krynetic.Database --help` for the capabilities and settings of your build, and test the commands your application uses before going to production.
- Protect the port with network controls. See [Security](../../Guides/Security.md).
