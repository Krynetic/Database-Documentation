# OIDC

**Default port:** `8250` · **Server name:** `OIDC`

An OpenID Connect interface.

## Start

```bash
Krynetic.Database --server OIDC
Krynetic.Database --server OIDC:<port>
```

## Connect

Use `http://localhost:8250` as the issuer address in your OpenID Connect client.

## Notes

- Use a standard client for the protocol; no Krynetic-specific library is needed.
- Data you write through this server is stored in the shared path tree and is visible through every other [server](../README.md). See [Concepts](../../Concepts/README.md).
- Run `Krynetic.Database --help` for the capabilities and settings of your build, and test the commands your application uses before going to production.
- Protect the port with network controls. See [Security](../../Guides/Security.md).
