# Type Casting

## Implicit

The JIT runtime compiler of JavaScript automatically can convert types based on usages.

```js
const foo = "foo";
const num = 1;

console.log(foo + num); // outputs "foo1" after casting the number to a string
```

## Explicit

Sometimes as a developer you want to force the type to be cast to another type. This is done using the built in methods;

- parseInt() // converts anything to an integer
- parseFloat() // converts anything to a float
- toString() // converts anything to a string

## Type coercion

This just means that implicit casting occurs in the runtime compiler.
