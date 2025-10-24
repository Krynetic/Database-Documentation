# Krynetic SPARQL

### `Default Endpoint` 
#### [http://localhost:3001](http://localhost:3001)

### Subjects

http://krynetic/ + `path name`

### Predicates

http://krynetic/ + `#value` \
http://krynetic/ + `#value.parent` \
http://krynetic/ + `#length`

### Objects

#### - Uri node
http://krynetic/ + `path name`

#### - Value node
"data"^^<http://www.w3.org/2001/XMLSchema#datatype>

---

## Query dummy data

```csharp
storage["users"] = new[]
{
    new { name = "admin" },
    new { name = "guest" },
    new { name = "neighbour" },
    new { name = "classmate" },
};

storage["static"] = "1";
```

## Query

```SQL
SELECT * WHERE { ?subject ?predicate ?object } LIMIT 100
```

| subject | predicate | object |
|---------|-----------|--------|
| <http://krynetic.com/users/0/name> | <http://krynetic.com/#value.parent> | <http://krynetic.com/users/0> |
| <http://krynetic.com/users/2/name> | <http://krynetic.com/#value.parent> | <http://krynetic.com/users/2> |
| <http://krynetic.com/users/3/name> | <http://krynetic.com/#value.parent> | <http://krynetic.com/users/3> |
| <http://krynetic.com/static> | <http://krynetic.com/#value.parent> | <http://krynetic.com/> |
| <http://krynetic.com/users/0/name> | <http://krynetic.com/#value> | "admin"^^<http://www.w3.org/2001/XMLSchema#string> |
| <http://krynetic.com/users/1/name> | <http://krynetic.com/#value> | "guest"^^<http://www.w3.org/2001/XMLSchema#string> |
| <http://krynetic.com/users/2/name> | <http://krynetic.com/#value> | "neighbour"^^<http://www.w3.org/2001/XMLSchema#string> |
| <http://krynetic.com/users/3/name> | <http://krynetic.com/#value> | "classmate"^^<http://www.w3.org/2001/XMLSchema#string> |
| <http://krynetic.com/static> | <http://krynetic.com/#value> | "1"^^<http://www.w3.org/2001/XMLSchema#string> |
| <http://krynetic.com/users/0> | <http://krynetic.com/#parent> | <http://krynetic.com/users> |
| <http://krynetic.com/users/1> | <http://krynetic.com/#parent> | <http://krynetic.com/users> |
| <http://krynetic.com/users/2> | <http://krynetic.com/#parent> | <http://krynetic.com/users> |
| <http://krynetic.com/users/3> | <http://krynetic.com/#parent> | <http://krynetic.com/users> |
| <http://krynetic.com/users> | <http://krynetic.com/#parent> | <http://krynetic.com/> |
| <http://krynetic.com/users/0> | <http://krynetic.com/#length> | "1"^^<http://www.w3.org/2001/XMLSchema#int> |
| <http://krynetic.com/users/1> | <http://krynetic.com/#length> | "1"^^<http://www.w3.org/2001/XMLSchema#int> |
| <http://krynetic.com/users/2> | <http://krynetic.com/#length> | "1"^^<http://www.w3.org/2001/XMLSchema#int> |
| <http://krynetic.com/users/3> | <http://krynetic.com/#length> | "1"^^<http://www.w3.org/2001/XMLSchema#int> |
| <http://krynetic.com/users> | <http://krynetic.com/#length> | "4"^^<http://www.w3.org/2001/XMLSchema#int> |
| <http://krynetic.com/> | <http://krynetic.com/#length> | "2"^^<http://www.w3.org/2001/XMLSchema#int> |

---

```SQL
SELECT * WHERE { 
  GRAPH <http://krynetic.com/users/0> {
    SELECT ?s ?p ?o WHERE { ?s ?p ?o }
  }
}
```

| subject | predicate | object |
|---------|-----------|--------|
| <http://krynetic.com/users/0> | <http://krynetic.com/#parent> | <http://krynetic.com/users> |
| <http://krynetic.com/users/0> | <http://krynetic.com/#length> | "1"^^<http://www.w3.org/2001/XMLSchema#int> |
| <http://krynetic.com/users/0/name> | <http://krynetic.com/#value> | "admin"^^<http://www.w3.org/2001/XMLSchema#string> |
| <http://krynetic.com/users/0/name> | <http://krynetic.com/#value.parent> |<http://krynetic.com/users/0> |

---

```SQL
SELECT * WHERE {
  GRAPH <http://krynetic.com/users> {
    SELECT ?name ?value WHERE {
      ?name <http://krynetic.com/#value> ?value .
    }
  }
}
```

| name | value |
|------|-------|
| <http://krynetic.com/users/0/name> | "admin"^^<http://www.w3.org/2001/XMLSchema#string> |
| <http://krynetic.com/users/1/name> | "guest"^^<http://www.w3.org/2001/XMLSchema#string> |
| <http://krynetic.com/users/2/name> | "neighbour"^^<http://www.w3.org/2001/XMLSchema#string> |
| <http://krynetic.com/users/3/name> | "classmate"^^<http://www.w3.org/2001/XMLSchema#string> |

---

```SQL
SELECT * WHERE { 
  GRAPH <http://krynetic.com/> {
    SELECT ?child WHERE {
      ?child <http://krynetic.com/#parent> <http://krynetic.com/> .
    }
  }
}
```

| child |
|-------|
| <http://krynetic.com/users> |

---

```SQL
SELECT * WHERE { 
  GRAPH <http://krynetic.com/users> {
    SELECT ?child WHERE {
      ?child <http://krynetic.com/#parent> <http://krynetic.com/users> .
    }
  }
}
```

| child |
|-------|
| <http://krynetic.com/users/0> |
| <http://krynetic.com/users/1> |
| <http://krynetic.com/users/2> |
| <http://krynetic.com/users/3> |

---

## Inserting data at a given path (*comming!*)

- `Path` \<http://krynetic.com/users/4/name>
- `Relation` \<http://krynetic.com/#value> (**REQUIRED**)
- `Value` "value"^^<http://www.w3.org/2001/XMLSchema#datatype>
```SQL
INSERT DATA {
  GRAPH <http://krynetic.com/users> {
    <http://krynetic.com/users/4/name> <http://krynetic.com/#value> "tester"^^<http://www.w3.org/2001/XMLSchema#string> .
  }
}
```


## Datatypes

| Type          | Description |
|------------------|-------------|
| `null`           | Represents no value |
| `byte`           | 8-bit unsigned integer |
| `sbyte`          | 8-bit signed integer |
| `ushort`         | 16-bit unsigned integer |
| `short`          | 16-bit signed integer |
| `uint`           | 32-bit unsigned integer |
| `int`            | 32-bit signed integer |
| `ulong`          | 64-bit unsigned integer |
| `long`           | 64-bit signed integer |
| `float`          | 32-bit floating-point |
| `double`         | 64-bit floating-point |
| `decimal`        | High-precision decimal |
| `string`         | Textual data |
| `boolean`        | True/False logical value |
| `dateTime`       | ISO 8601 date-time |
| `dateTimeStamp`  | Date-time with timezone |