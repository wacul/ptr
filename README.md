# ptr

Package 'ptr' provides utility functions to get the pointer of the built-in type.

## Why?

```
text := returnsString()
takesStringPtr(&text)

text = returnsString()
str := struct {
  text *string
} {
  text: &text,
}
```

↓

```
takesStringPtr(ptr.String(returnsString()))

str := struct {
  text *string
} {
  text: ptr.String(returnsString()),
}
```

It's so trivial, but that is I want.
