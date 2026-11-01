# Observability

## Logging

Set the minimum level with `--loglevel` (`-l`). From most to least verbose: `Trace`, `Debug`, `Information`, `Warning`, `Error`, `Critical`, `None`.

```bash
Krynetic.Database -s GraphQL -l Warning
```

At startup the log shows one line per server with its port, for example `GraphQL listening on port 8085`.

In Docker and Kubernetes read the logs with `docker logs` and `kubectl logs`.

## Live metrics table

`--metrics` shows application metrics in a continuously updating table in the console. Without arguments it shows everything. Pass patterns to filter them; patterns can be repeated, space-separated or comma-separated, and a leading `!` excludes matches.

```bash
Krynetic.Database -s GraphQL --metrics
Krynetic.Database -s GraphQL --metrics dotnet.*
Krynetic.Database -s GraphQL --metrics dotnet.* --metrics krynetic.database.dokan.*
Krynetic.Database -s GraphQL --metrics dotnet.*,krynetic.database.dokan.*
Krynetic.Database -s GraphQL --metrics dotnet.* '!*.debug'
```

On Windows, `--metrics-create-window` shows the table in a separate console window.

Enabling metrics also turns on per-server metrics for the running servers.

## OpenTelemetry

Export traces and metrics to an OpenTelemetry collector:

```bash
Krynetic.Database -s GraphQL --opentelemetry http://otel.company.com:4317
```

The short option is `-ot`. Point it at the OTLP endpoint of your collector (port `4317` is the conventional gRPC port).

## Health checks

Use the [Kubernetes probe server](../Servers/KubernetesProbe/README.md) for HTTP health checks.

## Interactive shell

`--shell` (`-sh`) opens an interactive shell on the console after startup, useful to inspect the data and try commands without a client. `--commands` prints the available commands and functions and exits.
