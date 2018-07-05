# Functions Composition

## ECMAScript 6
```javascript
const compose = (...fns) =>
    (arg) =>
        fns.reduce(
            (composed, f) => f(composed),
            arg
        )
```

## Ruby
```ruby
compose = -> (*functions) {
  -> (arg) {
    functions.inject(arg) { |acc, function|
      function.(acc)
    }
  }
}

```
