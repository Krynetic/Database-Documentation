# FTP

**Default port:** `2121` · **Server name:** `FTP`

Connect FTP clients to the store. The port is unprivileged (`2121`) so the server can run without elevated rights.

## Start

```bash
Krynetic.Database --server FTP
Krynetic.Database --server FTP:<port>
```

## Connect

Connect any FTP client to host `localhost`, port `2121`.

## Notes

- Use a standard client for the protocol; no Krynetic-specific library is needed.
- Data you write through this server is stored in the shared path tree and is visible through every other [server](../README.md). See [Concepts](../../Concepts/README.md).
- Run `Krynetic.Database --help` for the capabilities and settings of your build, and test the commands your application uses before going to production.
- Protect the port with network controls. See [Security](../../Guides/Security.md).
