# Configuration

## Environment variables

| Variable | Purpose | Example |
|---|---|---|
| `STORAGE_DIRECTORY` | Directory where data is stored. Equivalent to `--storage-directory`. | `/data` |
| `LICENSE_FILE` | Path to the license file (licensed edition). Equivalent to `--license-file`. | `/license.key` |
| `HOST` | Bind address for the servers. `*` listens on all interfaces, which is what you need inside a container or pod. | `*` |

Command-line options take precedence over environment variables when both are set.

## Persistent storage

Set a storage directory and mount it on durable storage:

- **Docker:** a named volume or bind mount (`-v krynetic-data:/data -e STORAGE_DIRECTORY=/data`). See [Docker](Docker.md).
- **Kubernetes:** a `PersistentVolumeClaim` with `ReadWriteOnce` access. See [Kubernetes](Kubernetes.md).

If no storage directory is configured, data is kept only for the life of the container.

Run **one instance per storage directory**. Never mount the same volume into two running instances, and keep Kubernetes deployments at `replicas: 1`.

## Editions and licensing

- **Community edition** starts without a license.
- **Licensed edition** starts with a license file passed through `--license-file` or `LICENSE_FILE`.

Some command-line options are available only in the licensed edition. Where this applies it is noted in the [command-line reference](../Commandline.md).

Keep license files in secrets (a Kubernetes `Secret`, a Docker secret, or a restricted file).

## Stopping cleanly

Stop the process with a normal termination signal (`docker stop`, pod termination) and allow a grace period of at least 30 seconds so that pending work finishes. In Kubernetes set `terminationGracePeriodSeconds: 30` or higher.

## Selecting servers and settings

- Choose which protocol servers start with `--server`. See [Servers](../Servers/README.md).
- Set server-specific settings with `--server-config`. See [Command line](../Commandline.md#server-specific-settings).
