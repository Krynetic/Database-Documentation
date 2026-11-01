# SSH and SFTP

**Default port:** `22` · **Server names:** `SSH`, `SFTP`

`SSH` and `SFTP` share one listener. Naming `SSH` enables the interactive shell, naming `SFTP` enables file transfer. Name both to enable both.

## Start

```bash
Krynetic.Database --server SSH --server SFTP
Krynetic.Database --server SSH:<port> --server SFTP:<port>
```

## Connect

```bash
# Port 22 needs elevated privileges on most systems, so use a high port when running directly on a host
Krynetic.Database --server SSH:2222 --server SFTP:2222

ssh  -p 2222 localhost
sftp -P 2222 localhost
```

## Notes

- Only enable the parts you need: `--server SSH` for the shell, `--server SFTP` for file transfer.
- Use a standard client for the protocol; no Krynetic-specific library is needed.
- Data you write through this server is stored in the shared path tree and is visible through every other [server](../README.md). See [Concepts](../../Concepts/README.md).
- Run `Krynetic.Database --help` for the capabilities and settings of your build, and test the commands your application uses before going to production.
- Protect the port with network controls. See [Security](../../Guides/Security.md).
