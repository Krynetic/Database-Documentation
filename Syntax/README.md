# Expression syntax

Expressions calculate values. Write one into a property whose name ends in `.expression` (see [Computed values](../Concepts/Computed-Values.md)), or run one on demand with the [`expression` operation](../Operations.md#expression).

## Pseudo-code used in these docs

Examples on this page use a neutral pseudo-code for operations. Use your server's own syntax ([GraphQL](../Servers/GraphQL/README.md), [gRPC](../Servers/GRPC/README.md), …) in real code.

```text
set /blog/title "My blog"
get /blog/title
subscribe /blog/title
```

Assign and re-assign:

```text
set /blog/title "My blog"
set /blog/title "My new blog"
```

Automate a title that updates every 15 seconds:

```text
set /@Schedule/blog {
  Expression "*/15 * * * * *"
  Target "/blog"
  Content {
    title.expression "'Welcome to my blog, time is ' + now()"
  }
}
```

Subscribe to it:

```text
subscribe /blog/title
- Response 1: "Welcome to my blog, time is 2026-10-27 20:00:00 +00:00"
- Response 2: "Welcome to my blog, time is 2026-10-27 20:00:15 +00:00"
- Response 3: "Welcome to my blog, time is 2026-10-27 20:00:30 +00:00"
```

Or read it once:

```text
get /blog/title
- Response: "Welcome to my blog, time is 2026-10-27 20:00:45 +00:00"
```

## Expression basics

| Element | Syntax | Example |
|---|---|---|
| String literal | single quotes | `'text'` |
| Number | digits, optional decimals | `42`, `3.14` |
| Arithmetic | `+ - * /` | `price * quantity` |
| String concatenation | `+` | `'Total: ' + total` |
| Function call | `name(arguments)` | `now()`, `pow(2, 8)` |
| Value in the same node | the plain name | `price` |
| Value anywhere | `Lookup("/path")` or `$("/path")` | `$("/order/total")` |

### Names resolve relative to the expression

In an expression stored at `/order/total.expression`, the name `price` refers to `/order/price`.

```text
/order/price                ->  9.5
/order/quantity             ->  4
/order/total.expression     ->  price * quantity       (result: 38)
/summary/text.expression    ->  'Total is ' + $("/order/total")
```

### Calling functions

Functions are grouped in categories (math, string, date, hashing, …). See [Using functions](../Guides/Using-Functions.md) and the [function reference](../Functions/README.md).

```text
now()
pow(2, 8)
$("/config/greeting") + ' ' + name
```

See the function reference for the exact names and signatures of the functions available in your build.

## Where expressions can run

| Place | How |
|---|---|
| A computed value | A property named `<name>.expression` |
| A one-off calculation | `{ _op: "expression", value: "now()" }`, see [Operations](../Operations.md#expression) |
| A scheduled write | `Content` of a [schedule](../Handlers/Schedule.md) |
