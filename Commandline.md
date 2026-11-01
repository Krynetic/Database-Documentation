# Command line

```text
Krynetic.Database [command] [options]
```

In the container image the entry point is already `Krynetic.Database`, so arguments go straight after the image name (`docker run … image --server GraphQL`) or into `command:` / `args:` in Compose and Kubernetes.

Run `--help` for the options available in your build and `--commands` for the built-in command and function reference.

## Options

| Option | Alias | Argument | Description |
|---|---|---|---|
| `--server` | `-s` | `Name[:port]` (repeatable) | Servers to start. At least one is required. See [Selecting servers](#selecting-servers-and-ports). |
| `--server-config` | | `Server key value` | Sets a server-specific setting. Repeatable. See [Server-specific settings](#server-specific-settings). |
| `--storage-directory` | `-sd` | path | Directory used for persistent storage. Defaults to the `STORAGE_DIRECTORY` environment variable. May be licensed-edition only. |
| `--license-file` | | path | License file for the licensed edition. |
| `--loglevel` | `-l` | level | Minimum log level: `Trace`, `Debug`, `Information`, `Warning`, `Error`, `Critical`, `None`. Default `Information`. |
| `--shell` | `-sh` | none | Starts an interactive shell after startup. |
| `--opentelemetry` | `-ot` | URL | OpenTelemetry collector to export telemetry to. |
| `--metrics` | | patterns (optional) | Shows live metrics in an updating table. See [Observability](Guides/Observability.md#live-metrics-table). |
| `--metrics-create-window` | | none | Shows the metrics table in a separate console window. Windows only. |
| `--optimize-socket` | | none | Applies Windows/Linux-specific socket optimizations. May be licensed-edition only. |
| `--export-to-file` | | path | Exports the data to a JSON backup file. |
| `--import-from-file` | | path | Imports data from a JSON backup file. The file must exist. |
| `--prefill` | | none | Fills the store with dummy data. For evaluation and testing only. |
| `--enable-experimental` | | none | Enables experimental options and servers. |
| `--commands` | | none | Displays the command and function reference. |
| `--version` | | none | Shows version information. |
| `--help` | `-h`, `-?` | none | Shows help and usage information. |

## Examples

Start GraphQL on its default port with persistent storage:

```bash
Krynetic.Database --storage-directory /var/lib/krynetic --server GraphQL
```

Licensed edition with three servers and telemetry:

```bash
Krynetic.Database \
  --license-file /path/to/license.lic \
  --storage-directory /data/store \
  --server MQTT \
  --server GraphQL \
  --server SocketIO \
  --opentelemetry http://otel.company.com:4317
```

Interactive shell and verbose logging:

```bash
Krynetic.Database -sd ./data -s GraphQL -sh -l Debug
```

## Selecting servers and ports

`--server` takes one or more server names. A port can be attached with a colon or given as the following token. These are all valid:

```bash
--server GraphQL
--server MongoDB:1337
--server MongoDB 1337
--server MongoDB:1337 SQL 1234 GraphQL
--server MongoDB:1337 SQL:1234 GraphQL
--server MongoDB:1337 --server GraphQL --server SQL
```

Rules:

- Server names are case-insensitive.
- Ports must be between 1 and 65535.
- A port must follow a server name.
- Naming a server twice keeps the last occurrence.
- Without a port the server's [default port](Reference/README.md#default-ports) is used.

Valid names: `Announce`, `AMQP`, `Couchbase`, `CouchDB`, `FTP`, `GraphQL`, `GRPC`, `HTTP` (OpenAPI), `KubernetesProbe`, `MongoDB`, `MQTT`, `OData`, `OIDC`, `Redis`, `S3`, `SFTP`, `SocketIO`, `Sparql`, `SQL`, `SSH`, `VirtualDisk`, `WCF`. Servers marked experimental in `--help` need `--enable-experimental`.

`SSH` and `SFTP` share one listener: `SSH` enables the interactive shell and `SFTP` enables file transfer. Name both to enable both.

See [Servers](Servers/README.md) for what each one does.

## Server-specific settings

```bash
--server-config <server> <key> <value>
```

Example:

```bash
Krynetic.Database \
  --server MongoDB \
  --server-config MongoDB adminuser root \
  --server-config MongoDB adminpassword "change-me"
```

Rules:

- The tokens after `--server-config` come in groups of three: server, key, value.
- Server names and keys are case-insensitive.
- A key the server does not define is rejected. `--help` lists the supported keys for every server.
- Values are typed automatically: whole numbers are integers, `true`/`false` are booleans, decimals are floating-point numbers, anything else is text. To force a type use the [`@enc:`](Concepts/Data-Types.md#typed-string-encoding) form, for example `@enc:string:12345`.

Documented settings:

| Server | Key | Type | Default | Description |
|---|---|---|---|---|
| [MongoDB](Servers/MongoDB/README.md) | `adminuser` | string | `admin` | Administrator user name |
| [MongoDB](Servers/MongoDB/README.md) | `adminpassword` | string | `pass` | Administrator password. **Change it.** |
| [SQL](Servers/SQL/README.md) | `maxmessagebody` | integer | `1000000` | Largest accepted message body in bytes |
| [SocketIO](Servers/SocketIO/README.md) | `welcomebanner` | string | built-in | Message sent to clients after connecting |
| [WCF](Servers/WCF/README.md) | `namespace` | string | `urn:KryneticWCF` | SOAP service namespace |
| [GraphQL](Servers/GraphQL/README.md#settings) | endpoint, transport, CORS | string | see `--help` | WebSocket sub-protocol and CORS settings |
| [VirtualDisk](Servers/VirtualDisk/README.md) | mount point, driver logging | string, bool | see `--help` | Where the disk mounts and whether the driver logs verbosely |

## Import and export

```bash
Krynetic.Database --storage-directory /data --export-to-file backup.json
Krynetic.Database --storage-directory /data --import-from-file backup.json
```

See [Backup and restore](Guides/Backup-and-Restore.md).

## Environment variables

| Variable | Equivalent |
|---|---|
| `STORAGE_DIRECTORY` | `--storage-directory` |
| `LICENSE_FILE` | `--license-file` |
| `HOST` | Bind address (`*` for all interfaces) |
