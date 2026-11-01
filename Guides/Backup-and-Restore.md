# Backup and restore

## What to protect

All data lives in the [storage directory](../Getting-Started/Configuration.md#persistent-storage). Protect it with regular exports and, for fast whole-instance recovery, volume snapshots.

## JSON export and import

Export the data to a JSON file:

```bash
Krynetic.Database --storage-directory /data --export-to-file backup.json
```

Import a previously exported file:

```bash
Krynetic.Database --storage-directory /data --import-from-file backup.json
```

- `--import-from-file` fails with `Cannot import file because it does not exist: '<path>'` when the path is wrong. Remember that paths are resolved inside the container when you use Docker.
- The export contains the whole path tree, including computed-value expressions and handler resources.
- Use export and import to move data between hosts, to upgrade between versions, and to keep readable backups.

With Docker:

```bash
docker run --rm \
  -v krynetic-data:/data -v "$PWD":/backup \
  -e STORAGE_DIRECTORY=/data \
  ghcr.io/krynetic/database-releases:latest \
  --export-to-file /backup/backup.json
```

Run exports and imports while no other instance is using the same storage directory.

## Volume snapshots

For fast backups: stop the instance (or scale the deployment to zero), snapshot the volume with your storage provider, and start it again. Do not copy the storage directory while the instance is running.

## Upgrading

1. Export the data with `--export-to-file`.
2. Stop the old version and keep its volume as a rollback copy.
3. Start the new image against a fresh volume and import the file with `--import-from-file`.
4. Check with a few reads, then switch clients over.

Pin explicit image tags for production so that upgrades are deliberate.

## Restore drill

Test restores regularly: start a throwaway instance on a new volume, import the latest export, and read a few known paths.
