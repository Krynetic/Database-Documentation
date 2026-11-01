# Computed values

A property whose name ends in `.expression` holds an [expression](../Syntax/README.md). The engine evaluates it, and the result is available under the name without the suffix.

```graphql
mutation {
  set(key: "/blog/title.expression", value: "'Welcome to my blog, time is ' + now()")
}

query {
  get(key: "/blog/title")
}
```

The query returns the calculated text, for example `Welcome to my blog, time is 2026-10-27 20:00:00 +00:00`.

You can also write the suffix as `_expression` (for example `title_expression`); it is treated as `title.expression`.

## Reading other values

Names in an expression that are not functions refer to other values, relative to the node that contains the expression.

```graphql
mutation {
  set(key: "/order", value: { price: 9.5, quantity: 4 })
  set(key: "/order/total.expression", value: "price * quantity")
}
```

`get(key: "/order/total")` returns `38`.

Use `Lookup("/absolute/path")` (alias `$("/absolute/path")`) to read a value from anywhere in the store.

## Automatic updates

The engine remembers which values an expression reads. When any of them change, the expression is calculated again and subscribers to the computed path are notified. Computed values can read other computed values.

## Time-based values

An expression that uses `now()` returns the time of its evaluation. To keep it fresh, drive it with a [schedule](../Handlers/Schedule.md).

## Errors

If an expression cannot be evaluated, the error names the expression and the reason (`Failed to evaluate '<expression>' due to …`). Correct the expression and write it again.

## Inside `@` paths

Expressions inside [handler](../Handlers/README.md) resources (paths that start with `/@`) are stored as text and are not evaluated there. They are evaluated when a handler writes them to their target, for example when a [schedule](../Handlers/Schedule.md) writes its `Content`.
