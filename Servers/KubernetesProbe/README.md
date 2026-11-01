# Kubernetes probe

**Default port:** `9999` · **Server name:** `KubernetesProbe`

A small HTTP server for container health checks. Responses are plain text.

```bash
Krynetic.Database --server GraphQL --server KubernetesProbe
```

## Endpoints

| Path | Healthy | Unhealthy | Use for |
|---|---|---|---|
| `/health/startup` | `200 started` | `503 starting` | `startupProbe` |
| `/health/ready` | `200 ready` | `503 not ready` | `readinessProbe` |
| `/health/live` | `200 alive` | `503 unhealthy` | `livenessProbe` |
| any other path | | `404`, listing the available paths | |

The readiness and liveness checks read from the store and fail with `503` when the store does not answer within one second.

```bash
curl -i http://localhost:9999/health/ready
```

## Kubernetes configuration

```yaml
          args: ["--server", "graphql", "--server", "KubernetesProbe"]
          startupProbe:
            httpGet: { path: /health/startup, port: 9999 }
            failureThreshold: 30
            periodSeconds: 2
          readinessProbe:
            httpGet: { path: /health/ready, port: 9999 }
            periodSeconds: 5
          livenessProbe:
            httpGet: { path: /health/live, port: 9999 }
            periodSeconds: 10
```

See [Kubernetes](../../Getting-Started/Kubernetes.md) for the full manifest.
