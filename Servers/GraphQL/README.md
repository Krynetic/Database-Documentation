# Krynetic GraphQL

### `Default Endpoint` 
#### [http://localhost:8085](http://localhost:8085)

## `get`

### Get data at a certain path

```cpp
query {
  get(key: "/")
}
```

**Response**:
```json
{
  "blog": {
    "title": "My blog",
    "data": ...
  }
}
```

## `set`

### Set data at a certain path

```cpp
mutation {
  set(key: "/", value: {
    blog: {
      title: "My blog",
      data: {
        one: 1,
        two: "2",
        three: 3.0
      }
    }
  })
}
```

**Response**:
`JSON`

## `subscribe`

### Continuously listens for new data at a given path.

```cpp
subscription {
  subscribe(key: "/") {
    path
    value
  }
}
```

**Response**:
`Streaming JSON`

```json
{
  "path": "blog/title",
  "value": "My blog"
}
```