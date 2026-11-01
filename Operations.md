# Operations

An operation modifies the value at a path on the server instead of replacing it. Send an operation as an **object value** with the reserved key `_op`, plus `value` where the operation needs an argument.

Operations run in the server, so concurrent clients do not overwrite each other the way a read-modify-write cycle in the client can. Two clients that increment a counter at the same moment both count.

The examples use [GraphQL](Servers/GraphQL/README.md). The same object can be sent through any server that lets you write a structured JSON value, for example with [WCF](Servers/WCF/README.md):

```csharp
await client.SetAsync("/number1", "{\"_op\":\"increment\",\"value\":3}");
```

## Summary

| Operation | Applies to | Argument | Effect |
|---|---|---|---|
| [`add`](#add) | any | `value` | Adds new data. Same as an ordinary assignment |
| [`remove`](#remove) | any | none | Removes the property |
| [`toggle`](#toggle) | bool | none | Flips `true` to `false` and `false` to `true` |
| [`increment`](#increment) | number | `value` | Adds `value` |
| [`decrement`](#decrement) | number | `value` | Subtracts `value` |
| [`multiply`](#multiply) | number | `value` | Multiplies by `value` |
| [`divide`](#divide) | number | `value` | Divides by `value` |
| [`test`](#test) | any | `value` | Compares the stored value with `value` and stores `true` or `false` |
| [`append`](#append) | string | `value` | Appends text |
| [`appendline`](#append-line) | string | `value` | Appends text followed by a new line |
| [`rename`](#rename) | any | `value` (new name) | Renames the property |
| [`expression`](#expression) | any | `value` (expression) | Evaluates an expression and assigns the result |

## Setup used by the examples

```graphql
mutation {
  set(key: "/str1", value: "Hello")
  set(key: "/bool1", value: false)
  set(key: "/number1", value: 1)
}
```

## add

Adds new data. This is the same as a normal assignment but is accepted as an operation.

```graphql
mutation {
  set(key: "/bool1", value: { _op: "add", value: true })
}
```

## remove

Removes the property from the database.

```graphql
mutation {
  set(key: "/bool1", value: { _op: "remove" })
}
```

## toggle

Flips a boolean.

```graphql
mutation {
  set(key: "/bool1", value: { _op: "toggle" })
}
```

## increment

Adds the given amount to a number.

```graphql
mutation {
  set(key: "/number1", value: { _op: "increment", value: 3 })
}
```

## decrement

Subtracts the given amount from a number.

```graphql
mutation {
  set(key: "/number1", value: { _op: "decrement", value: 3 })
}
```

## multiply

Multiplies a number by the given amount.

```graphql
mutation {
  set(key: "/number1", value: { _op: "multiply", value: 3 })
}
```

## divide

Divides a number by the given amount.

```graphql
mutation {
  set(key: "/number1", value: { _op: "divide", value: 3 })
}
```

## test

Compares the existing value with the given value and sets the same property to `true` or `false`.

```graphql
mutation {
  set(key: "/str1", value: { _op: "test", value: "Some value" })
}
```

## append

Appends text to an existing string.

```graphql
mutation {
  set(key: "/str1", value: { _op: "append", value: " World!" })
}
```

## append line

Appends text to an existing string and ends it with a new line (`\n`). Useful for log-style values: each call adds one line.

```graphql
mutation {
  set(key: "/log", value: { _op: "appendline", value: "more text i want appended to logfile" })
}
```

## rename

Renames a property.

```graphql
mutation {
  set(key: "/str1", value: { _op: "rename", value: "str2" })
}
```

## expression

Executes any built-in [expression](Syntax/README.md) and assigns the result to the same property.

```graphql
mutation {
  set(key: "/the_time", value: { _op: "expression", value: "now()" })
}
```

## Operations in schedules

An operation can be the `Content` of a [schedule](Handlers/Schedule.md), for example a heartbeat counter:

```text
set /@Schedule/heartbeat {
  Expression "10s"
  Target "/status/heartbeat"
  Content { _op "increment" value 1 }
}
```
