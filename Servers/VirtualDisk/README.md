# Virtual disk

**Server name:** `VirtualDisk` · **Port:** none (file-system mount)

Mounts the store as a drive or directory on the host operating system, so ordinary tools can browse the path tree as folders and files.

| Platform | Driver | Source
|---|---|---|
| Windows | Dokan | https://github.com/dokan-dev/dokany |
| Linux | FUSE | apt, apk, dnf, pacman |

## Prerequisites

- **Windows:** install the Dokan driver.
- **Linux:** install FUSE (`fuse3`) and make `/dev/fuse` available to the process. In a container that means adding the device and the `SYS_ADMIN` capability.

## Start

```bash
Krynetic.Database --server VirtualDisk
```

## Settings

| Setting | Description |
|---|---|
| Mount point | Where the disk is mounted (a drive letter on Windows, a directory on Linux) |
| Driver logging | Switch for verbose driver logging |

Run `--help` for the exact key names and defaults and set them with `--server-config VirtualDisk <key> <value>`. See [Command line](../../Commandline.md#server-specific-settings).

## Notes

- When metrics are enabled, filter for the driver with `--metrics krynetic.database.dokan.*`. See [Observability](../../Guides/Observability.md).
- Data written through the disk is shared with every other [server](../README.md).
