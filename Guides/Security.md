# Security

Every server you start is a network service. Treat each one that way.

1. **Start only the servers you need.** Each extra server is an extra port to protect.
2. **Set credentials before exposing a server.** The [MongoDB server](../Servers/MongoDB/README.md) uses the default user `admin` with password `pass`. Set `adminuser` and `adminpassword` with `--server-config` first.
3. **Terminate TLS in front of HTTP-based servers.** GraphQL, gRPC, Socket.IO, WCF, SPARQL and the HTTP servers listen without TLS by default. Use a reverse proxy, ingress controller or service mesh.
4. **Restrict CORS.** Set the GraphQL allowed origin to your application's origin, not a wildcard.
5. **Restrict network access.** In Kubernetes use a [`NetworkPolicy`](../Getting-Started/Kubernetes.md#restrict-access). In Docker, bind published ports to loopback where possible (`-p 127.0.0.1:8085:8085`).
6. **Treat expression and handler writes as privileged.** Anyone who can write a `.expression` property or a resource under an `@` path can run [functions](Using-Functions.md) on the server, including functions that make outgoing network calls, run scripts or manage containers. Allow it only for trusted clients and put an authenticating gateway in front of write-capable servers.
7. **Keep license keys in secrets.** Use a Kubernetes `Secret` (not a ConfigMap) and a Docker secret or restricted file elsewhere.
8. **Pin image versions** and upgrade deliberately. See [Backup and restore](Backup-and-Restore.md#upgrading).
9. **Run one instance per storage directory.** Never mount the same volume into two running instances.
10. **Back up regularly** and test restores.

## Checklist before going live

- [ ] Only required servers are started
- [ ] Default credentials changed
- [ ] TLS in front of HTTP-based servers
- [ ] CORS origin restricted
- [ ] Ports reachable only by intended clients
- [ ] Write access limited to trusted clients
- [ ] License stored as a secret
- [ ] Image tag pinned
- [ ] Backups scheduled and a restore tested
