# Handlers

A **handler** is a declarative resource: you write a node under the handler's `@` namespace, and Krynetic starts the work the node describes and keeps it running.

```text
/@<Handler>/<resource-name>   ->   configuration properties
```

## Lifecycle

- **Create** a resource with valid configuration and it starts.
- **Change** its configuration and it restarts with the new configuration.
- **Remove** the node and it stops.
- State that the handler reports back (for example the last time a schedule ran) is written into the resource's node. Reported state does not count as a configuration change, so it does not restart the resource.
- A resource with an **invalid** configuration does not start.
- Resources are stored with your data, so they start again after a restart when you use [persistent storage](../Getting-Started/Configuration.md#persistent-storage).

## Available handlers

| Namespace | Page |
|---|---|
| `/@Schedule` | [Schedule](Schedule.md): time-based writes |
| `/@AccessTokens` | Access tokens |
| `/@CMD` | Command execution |
| `/@Containers` | Containers |
| `/@EmailSync` | E-mail synchronization |
| `/@GraphQL` | Outgoing GraphQL integration |
| `/@Ldap` | LDAP integration |
| `/@Mqtt` | Outgoing MQTT integration |
| `/@Sql` | Outgoing SQL integration |
| `/@Template` | Templates |
| `/@Torrent` | Torrents |
| `/@WebSocket` | Outgoing WebSocket integration |

Handler names are case-insensitive. Run `Krynetic.Database --commands` for the handlers and functions in your build.

## Expressions inside handler resources

Values inside `@` paths are stored as written; expressions there are not evaluated in place. They are evaluated when the handler writes them to its target. See [Computed values](../Concepts/Computed-Values.md#inside--paths).

## Who may create handlers

Handlers can run commands, contact other systems and manage containers. Only trusted clients should be allowed to write under `@` paths. See [Security](../Guides/Security.md).
