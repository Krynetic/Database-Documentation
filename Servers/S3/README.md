# S3

**Default port:** `9000` · **Server name:** `S3`

Connect S3 SDKs and tools to the store.

## Start

```bash
Krynetic.Database --server S3
Krynetic.Database --server S3:<port>
```

## Connect

Configure your SDK or CLI with the endpoint `http://localhost:9000`:

```bash
aws --endpoint-url http://localhost:9000 s3 ls
```

## Notes

- Use a standard client for the protocol; no Krynetic-specific library is needed.
- Data you write through this server is stored in the shared path tree and is visible through every other [server](../README.md). See [Concepts](../../Concepts/README.md).
- Run `Krynetic.Database --help` for the capabilities and settings of your build, and test the commands your application uses before going to production.
- Protect the port with network controls. See [Security](../../Guides/Security.md).
