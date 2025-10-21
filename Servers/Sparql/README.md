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

## Query

```SQL
SELECT * WHERE { ?subject ?predicate ?object } LIMIT 100
```

| subject | predicate | object |
|---|---|---|
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

----

## Dummy data used

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