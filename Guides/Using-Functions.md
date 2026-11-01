# Using functions

Functions extend [expressions](../Syntax/README.md). They are provided by built-in plugins grouped in categories: math, strings, dates, hashing, encryption, HTTP, scripting and more. The [function reference](../Functions/README.md) lists every function with its signature.

`Krynetic.Database --commands` prints the commands and functions available in your build.

## Where you can call a function

| Place | Example |
|---|---|
| A computed value | `set /blog/title.expression "'Hello ' + Now()"` |
| A one-off [operation](../Operations.md#expression) | `{ _op: "expression", value: "Now()" }` |
| The `Content` of a [schedule](../Handlers/Schedule.md) | `"now.expression": "Now()"` |

## Reading signatures

```text
function [pure] Lookup(string fullkey = "") -> object   (alias $)
```

- `[pure]` means the function has no side effects.
- `[may modify]` means the function can change state (for example it builds an array or writes data).
- A parameter with `= value` is optional.
- `param type[] name` accepts any number of arguments.
- Some functions have aliases, such as `$` for `Lookup`.

## Core functions

| Function | Returns | Description |
|---|---|---|
| `Lookup(fullkey)` / `$(fullkey)` | object | Reads a value from the store by absolute path |
| `Parent()` | string | Path of the parent node of the expression |
| `Self()` | string | Path of the expression itself |
| `Length(obj)` | int | Length of a string, array or node |
| `Type(data)` | database type | The database type of a value |
| `ToBytes(value)` | byte[] | Converts a value to bytes |
| `Array(items…)` | object[] | Builds an array from the arguments (`[may modify]`) |

### Examples

Read a value from anywhere:

```text
/summary/text.expression  ->  'Total is ' + $("/order/total")
```

## Categories

Each category has its own page in the [function reference](../Functions/README.md):

| Category |
|---|
| [Advanced Encryption Standard (AES)](../Functions/Advanced%20Encryption%20Standard%20%28AES%29.md) |
| [Barcode](../Functions/Barcode.md) |
| [Built-In](../Functions/Built-In.md) |
| [CSharp](../Functions/CSharp.md) |
| [Cache](../Functions/Cache.md) |
| [Captcha](../Functions/Captcha.md) |
| [Colors](../Functions/Colors.md) |
| [Compression](../Functions/Compression.md) |
| [Containers](../Functions/Containers.md) |
| [Conversions](../Functions/Conversions.md) |
| [Cookies](../Functions/Cookies.md) |
| [Date](../Functions/Date.md) |
| [Documentation](../Functions/Documentation.md) |
| [Elliptic Curve Digital Signature Algorithm (ECDSA)](../Functions/Elliptic%20Curve%20Digital%20Signature%20Algorithm%20%28ESDSA%29.md) |
| [Emojis](../Functions/Emojis.md) |
| [Encoding](../Functions/Encoding.md) |
| [Environment](../Functions/Environment.md) |
| [Exchange rate](../Functions/Exchange%20rate.md) |
| [Extraction](../Functions/Extraction.md) |
| [Geolocation](../Functions/Geolocation.md) |
| [Globally Unique Identifier (Guid)](../Functions/Globally%20Unique%20Identifier%20%28Guid%29.md) |
| [Hash-based Message Authentication Code (HMAC)](../Functions/Hash-based%20Message%20Authentication%20Code%20%28HMAC%29.md) |
| [Hashing](../Functions/Hashing.md) |
| [Hypertext Transfer Protocol (HTTP)](../Functions/Hypertext%20Transfer%20Protocol%20%28HTTP%29.md) |
| [JSON Web Token (JWT)](../Functions/JSON%20Web%20Token%20%28JWT%29.md) |
| [JSON](../Functions/JSON.md) |
| [JavaScript](../Functions/JavaScript.md) |
| [Large Language Model (LLM)](../Functions/Large%20Language%20Model%20%28LLM%29.md) |
| [Lookup](../Functions/Lookup.md) |
| [Lua](../Functions/Lua.md) |
| [Math](../Functions/Math.md) |
| [Multipurpose Internet Mail Extensions (MIME)](../Functions/Multipurpose%20Internet%20Mail%20Extensions%20%28MIME%29.md) |
| [Networking](../Functions/Networking.md) |
| [One-Time Password (OTP)](../Functions/One-Time%20Password%20%28OTP%29.md) |
| [Parsing](../Functions/Parsing.md) |
| [Password](../Functions/Password.md) |
| [Path](../Functions/Path.md) |
| [Print](../Functions/Print.md) |
| [Python](../Functions/Python.md) |
| [Random](../Functions/Random.md) |
| [Really Simple Syndication (RSS)](../Functions/Really%20Simple%20Syndication%20%28RSS%29.md) |
| [Regex](../Functions/Regex.md) |
| [Rivest Shamir Adleman (RSA)](../Functions/Rivest%20Shamir%20Adleman%20%28RSA%29.md) |
| [Roman Numerals](../Functions/Roman%20Numerals.md) |
| [Ruby](../Functions/Ruby.md) |
| [Secure String](../Functions/Secure%20String.md) |
| [String Casing](../Functions/String%20Casing.md) |
| [String](../Functions/String.md) |
| [System](../Functions/System.md) |
| [Temperature](../Functions/Temperature.md) |
| [Templating](../Functions/Templating.md) |
| [Uniform Resource Locator (URL)](../Functions/Uniform%20Resource%20Locator%20%28URL%29.md) |
| [User agent (UA)](../Functions/User%20agent%20%28UA%29.md) |
| [Validation](../Functions/Validation.md) |
| [Weather](../Functions/Weather.md) |
| [Wifi](../Functions/Wifi.md) |
| [X509Certificates](../Functions/X509Certificates.md) |

## Functions that reach outside Krynetic

Some functions contact other systems or run other code: HTTP, weather, exchange rates, language models, containers and the scripting languages (C#, JavaScript, Lua, Python, Ruby). They need the matching network access or runtime, and anyone who can write an expression can use them. Limit who can write expressions to trusted clients. See [Security](Security.md).
