## Syntax
### All examples will use pseudo code

#### Assigns "My blog" to path /blog/title
```cpp
set /blog/title "My blog"
```

#### Re-assign /blog/title with a new updated value "My new blog"
```cpp
set /blog/title "My new blog"
```

#### Automate updating the blog title every 15 seconds
```cpp
set /@Schedule/blog {
  Expression "*/15 * * * * *"
  Target "/blog"
  Content {
    title.expression "'Welcome to my blog, time is ' + now()"
  }
}
```

#### Which can be `subscribed` to
```cpp
subscribe /blog/title
- Response 1: "Welcome to my blog, time is 2025-01-30 00:00:00 +00:00"
- Response 2: "Welcome to my blog, time is 2025-01-30 00:00:15 +00:00"
- Response 3: "Welcome to my blog, time is 2025-01-30 00:00:30 +00:00"
- Response 4: "Welcome to my blog, time is 2025-01-30 00:00:45 +00:00"
```

#### Or do an ordinary `get`
```cpp
get /blog/title
- Response: "Welcome to my blog, time is 2025-01-30 00:00:45 +00:00"
```