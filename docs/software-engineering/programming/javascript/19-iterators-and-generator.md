# Iterators and generators

## Iterators

The idea of an iterator is to loop through an array / collection of data. Typically this is done with `for` and `while` loops.

## Generators

Anything that has the capability of creating a sequence is a generator.

```js
function positiveInts(n) {
  var i = 1;
  var max = n < 1 || typeof n !== "number" ? 1 : n;
  return {
    next: function () {
      if (i > max) return { value: undefined, done: true };
      return { value: i++, done: false };
    },
  };
}

var seq = positiveInts(3);

seq.next(); // {value: 1, done: false}
seq.next(); // {value: 2, done: false}
seq.next(); // {value: 3, done: false}
seq.next(); // {value: undefined, done: true}
```

### Generator function

An asterisk `*`\* is used to define a generator function.

```js
function* myGenerator() {
  // do things
}
```

The **yield** keyword is used to define a value in the iterable sequence.

```js
function* sequence() {
  yield 1;
  yield 3;
  yield 5;
}

var seq = sequence();

seq.next(); // {value: 1, done: false}
seq.next(); // {value: 3, done: false}
seq.next(); // {value: 5, done: false}
seq.next(); // {value: undefined, done: true}
```

The code `var seq = sequence();` does not execute the logic inside the `sequence()` function but rather just gets an instance of the generator.

When the call `next()` is made on the sequence instance each of the yield values is returned one by one.

Each time the sequence is called it goes through the code until a `yield` is reached and then pauses the execution. The current position is internally retained in the generator function. On subsequent calls it moves again from the last position until the next `yield`.

- next() resumes execution within the generator.
- yield pauses execution within the generator.
