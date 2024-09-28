# Loops

## For

For loops go from a start position to an end position of an interable object.

```js
for (let i = 0; i < array.length; i++) {
  console.log(array[i]);
}
```

### Break

While inside a `for` loop if you use the `break` syntax then the execution will skip to outside the for loop.

### Continue

While inside a `for` loop if you use the `continue` syntax then the execution will just to the next iteration in the loop.

## While

A while loop will execute until the condition is false.

```js
while (age < 50) {
  console.log(age);
  age++;
}
```

## Do...while

A `do...while` loop will execute until the while condition is false. The difference from a while loop is that it will execute at least once, as the condition check only happens at the end of each execution.

## For...of

A `for...of` loop will iterate through an iterable object. It is cleaner than using a standard for loop as long as you don't need to know the index position.

```js
const people = ["James", "Rita", "Mel"];
for (const name of people) {
  console.log(name);
}
```

## For...in

A `for...in` loop is used for iterating over an object. The value for each loop is the property key.

```js
const items = { a: 1, b: 2, c: 3 };
for (const item in items) {
  console.log(item, items[item]);
}
```

This will output;
a 1
b 2
c 3
