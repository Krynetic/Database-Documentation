# Data types

## Primitive types

| Type | Description |
|---|---|
| `null` | No value |
| `bool` | `true` / `false` |
| `byte`, `sbyte` | 8-bit unsigned / signed integer |
| `short`, `ushort` | 16-bit signed / unsigned integer |
| `int`, `uint` | 32-bit signed / unsigned integer |
| `long`, `ulong` | 64-bit signed / unsigned integer |
| `float`, `double` | 32-bit / 64-bit floating point |
| `decimal` | High-precision decimal |
| `string` | Text |
| `Guid` | Globally unique identifier |
| `DateTime`, `DateTimeOffset` | Date and time, without or with a UTC offset |
| `TimeSpan` | A duration |
| `byte[]` | Binary data |

Nodes (objects) and lists are described in [Concepts](README.md#nodes-and-values).

## Typed string encoding

Protocols and clients that can only carry text can still write a typed value by using an encoded string. The format is the prefix `@enc:`, a type name, a separator and the value:

```text
@enc:<type>:<value>
```

The separator after the type name may be `:` or a line break.

### Examples

```text
@enc:int32:42
@enc:int64:9000000000
@enc:double:3.14
@enc:decimal:19.99
@enc:bool:true
@enc:guid:3f2504e0-4f89-11d3-9a0c-0305e82c3301
@enc:datetime:2026-10-27T20:00:00.0000000Z
@enc:datetimeoffset:2026-10-27T20:00:00.0000000+01:00
@enc:timespan:00:05:00
@enc:string:plain text
@enc:json:{"a":1}
@enc:bytes:base64:SGVsbG8=
@enc:bytes:hex:48656c6c6f
@enc:bytes:bin:0100100001101001
@enc:null
@enc:dbnull
```

### Type names

| Type name | Aliases | Value format |
|---|---|---|
| `string` | | Any text |
| `bool` | | `true` or `false` |
| `byte` | | 0 to 255 |
| `sbyte` | | −128 to 127 |
| `short` | `int16` | 16-bit signed integer |
| `ushort` | `uint16` | 16-bit unsigned integer |
| `int` | `int32` | 32-bit signed integer |
| `uint` | `uint32` | 32-bit unsigned integer |
| `long` | `int64` | 64-bit signed integer |
| `ulong` | `uint64` | 64-bit unsigned integer |
| `float` | `single` | Floating-point number |
| `double` | | Floating-point number |
| `decimal` | | Decimal number |
| `guid` | | GUID text |
| `datetime` | | ISO 8601 date and time |
| `datetimeoffset` | | ISO 8601 date, time and offset |
| `timespan` | | `[d.]hh:mm:ss[.fffffff]` |
| `bytes` | | `base64:`, `hex:` or `bin:` followed by the data |
| `json` | | A JSON document |
| `null` | | none |
| `dbnull` | | none |

Numbers are parsed with the invariant culture, so the decimal separator is always `.`.

### Where it is used

- Command line: `--server-config MongoDB adminpassword "@enc:string:12345"` forces a numeric-looking password to stay text.
- Anywhere a Krynetic setting or value is given as text and parsed automatically, the `@enc:` form removes the guesswork.
