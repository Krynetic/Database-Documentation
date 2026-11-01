# SPARQL

**Default endpoint:** <http://localhost:3001> · **Server name:** `Sparql`

The SPARQL server presents the path tree as an RDF graph so that linked-data tooling can query it.

```bash
Krynetic.Database --server Sparql
```

## Mapping

**Subjects** are IRIs built from the path: `http://krynetic.com/` followed by the path (for example `http://krynetic.com/users/0/name`).

**Predicates**

| Predicate | Meaning |
|---|---|
| `http://krynetic.com/#value` | The stored value of a leaf |
| `http://krynetic.com/#value.parent` | The node that contains a leaf |
| `http://krynetic.com/#parent` | The parent of a node |
| `http://krynetic.com/#length` | The number of children of a node |

**Objects** are IRI nodes (a path IRI) or typed literals such as `"data"^^<http://www.w3.org/2001/XMLSchema#string>`.

## Example data

Create it through any server, for example GraphQL:

```graphql
mutation {
  set(key: "/users", value: [
    { name: "admin" }, { name: "guest" }, { name: "neighbour" }, { name: "classmate" }
  ])
  set(key: "/static", value: "1")
}
```

## Queries

### Everything

```sparql
SELECT * WHERE { ?subject ?predicate ?object } LIMIT 100
```

| subject | predicate | object |
|---|---|---|
| `<http://krynetic.com/users/0/name>` | `<http://krynetic.com/#value.parent>` | `<http://krynetic.com/users/0>` |
| `<http://krynetic.com/users/0/name>` | `<http://krynetic.com/#value>` | `"admin"^^<http://www.w3.org/2001/XMLSchema#string>` |
| `<http://krynetic.com/static>` | `<http://krynetic.com/#value>` | `"1"^^<http://www.w3.org/2001/XMLSchema#string>` |
| `<http://krynetic.com/users/0>` | `<http://krynetic.com/#parent>` | `<http://krynetic.com/users>` |
| `<http://krynetic.com/users>` | `<http://krynetic.com/#length>` | `"4"^^<http://www.w3.org/2001/XMLSchema#int>` |
| `<http://krynetic.com/>` | `<http://krynetic.com/#length>` | `"2"^^<http://www.w3.org/2001/XMLSchema#int>` |

### One node

Scope a query to a node with a `GRAPH` clause:

```sparql
SELECT * WHERE {
  GRAPH <http://krynetic.com/users/0> {
    SELECT ?s ?p ?o WHERE { ?s ?p ?o }
  }
}
```

| subject | predicate | object |
|---|---|---|
| `<http://krynetic.com/users/0>` | `<http://krynetic.com/#parent>` | `<http://krynetic.com/users>` |
| `<http://krynetic.com/users/0>` | `<http://krynetic.com/#length>` | `"1"^^<http://www.w3.org/2001/XMLSchema#int>` |
| `<http://krynetic.com/users/0/name>` | `<http://krynetic.com/#value>` | `"admin"^^<http://www.w3.org/2001/XMLSchema#string>` |
| `<http://krynetic.com/users/0/name>` | `<http://krynetic.com/#value.parent>` | `<http://krynetic.com/users/0>` |

### All values below a node

```sparql
SELECT * WHERE {
  GRAPH <http://krynetic.com/users> {
    SELECT ?name ?value WHERE {
      ?name <http://krynetic.com/#value> ?value .
    }
  }
}
```

| name | value |
|---|---|
| `<http://krynetic.com/users/0/name>` | `"admin"^^<http://www.w3.org/2001/XMLSchema#string>` |
| `<http://krynetic.com/users/1/name>` | `"guest"^^<http://www.w3.org/2001/XMLSchema#string>` |
| `<http://krynetic.com/users/2/name>` | `"neighbour"^^<http://www.w3.org/2001/XMLSchema#string>` |
| `<http://krynetic.com/users/3/name>` | `"classmate"^^<http://www.w3.org/2001/XMLSchema#string>` |

### Children of a node

```sparql
SELECT * WHERE {
  GRAPH <http://krynetic.com/users> {
    SELECT ?child WHERE {
      ?child <http://krynetic.com/#parent> <http://krynetic.com/users> .
    }
  }
}
```

Returns `users/0` to `users/3`. For the root, use `GRAPH <http://krynetic.com/>` and `#parent <http://krynetic.com/>`.

## Inserting data

`INSERT DATA` is planned and not yet available. When it ships it will use the path as subject, `#value` as the required predicate, and a typed literal as object:

```sparql
INSERT DATA {
  GRAPH <http://krynetic.com/users> {
    <http://krynetic.com/users/4/name> <http://krynetic.com/#value> "tester"^^<http://www.w3.org/2001/XMLSchema#string> .
  }
}
```

Until then, write through another [server](../README.md).

## Datatypes

| Type | Description |
|---|---|
| `null` | No value |
| `byte`, `sbyte` | 8-bit unsigned / signed integer |
| `ushort`, `short` | 16-bit unsigned / signed integer |
| `uint`, `int` | 32-bit unsigned / signed integer |
| `ulong`, `long` | 64-bit unsigned / signed integer |
| `float`, `double` | 32-bit / 64-bit floating point |
| `decimal` | High-precision decimal |
| `string` | Text |
| `boolean` | True / false |
| `dateTime` | ISO 8601 date and time |
| `dateTimeStamp` | Date and time with time zone |
