# Operations

## GraphQL used for examples

## Assume previous mutations
```cpp
mutation {
  set(key: "/str1", value: "Hello")
  set(key: "/bool1", value: false)
  set(key: "/number1", value: 1)
}
```

---

### **Add** 
#### Add new data *(same as normal assignment, but supported anyways)*
```cpp
mutation {
  set(key: "/bool1", value: {
    _op: "add",
    value: true
  })
}
```

### **Remove**
#### Removes property from database

```cpp
mutation {
  set(key: "/bool1", value: {
    _op: "remove"
  })
}
```

### **Toggle**
#### Toggles boolean value from true to false, and false to true

```cpp
mutation {
  set(key: "/bool1", value: {
    _op: "toggle"
  })
}
```

### **Increment**
#### Increments number by given value

```cpp
mutation {
  set(key: "/number1", value: {
    _op: "increment",
    value: 3
  })
}
```

### **Decrement**
#### Decrements number by given value

```cpp
mutation {
  set(key: "/number1", value: {
    _op: "decrement",
    value: 3
  })
}
```

### **Multiply**
#### Multiplies number by given value

```cpp
mutation {
  set(key: "/number1", value: {
    _op: "multiply",
    value: 3
  })
}
```

### **Divide**
#### Divides number by given value

```cpp
mutation {
  set(key: "/number1", value: {
    _op: "divide",
    value: 3
  })
}
```

### **Test**
#### Compares existing value with another value
#### Sets same property name to *true* or *false*

```cpp
mutation {
  set(key: "/str1", value: {
    _op: "test",
    value: "Some value"
  })
}
```

### **Append**
#### Appends more text to an existing string

```cpp
mutation {
  set(key: "/str1", value: {
    _op: "append",
    value: " World!"
  })
}
```

### **Append Line**
#### Appends more text to an existing string and ends with \n (new line)

```cpp
mutation {
  set(key: "/log", value: {
    _op: "appendline",
    value: "more text i want appended to logfile"
  })
}
```

### **Rename**
#### Renames a property to a new given name

```cpp
mutation {
  set(key: "/str1", value: {
    _op: "rename",
    value: "str2"
  })
}
```

### **Expression (powerfull)**
#### Executes any built-in expression and assigns it to same property

```cpp
mutation {
  set(key: "/the_time", value: {
    _op: "expression",
    value: "now()"
  })
}
```