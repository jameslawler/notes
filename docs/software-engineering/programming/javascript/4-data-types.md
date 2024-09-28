# Data Types

[MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures)

## Dynamic data types

As JavaScript is a dynamic language, variables are not bound to a specific type and can be changed during re-assigning a value.

```js
let foo = 42; // foo is a Number
foo = "bar"; // foo is now a String
foo = true; // foo is now a Boolean
```

As JavaScript is also weakly typed, it will do automatic implicit type conversions when necessary. This is adventagious, but can also lead to bugs when unexpected conversions occur.

```js
const foo = 42;
const result = foo + "1"; // foo is automatically converted to a string so it can be concatenated with "1"
console.log(result); // reuslt is "421"
```

## Primative data types

There are seven primative data types. These are immutable.

- Null
- Undefined
- Boolean
- Number
- BigInt
- String
- Symbol

### Null

It only has one value `null`

### Undefined

It also only has one value `undefined`.

Undefined means no value is set, whereas Null means a null has been explicitly set. Ways to get a undefined;

- If a function returns without a value, then `undefined` is returned.
- If you access a property on an object that doesn't exist, then `undefined` is returned.
- When a variable is declared but not initialized, then it is `undefined`.

### Boolean

True or False values

### Number

The Number type is a double precision 64 bit value capable of storing very large ranges of numbers.

Integers are only safe to be stored between -2^53 and 2^53.
Floating points are safe between -2^1074 and 2^1023.

- Positive numbers greater than Number.MAX_VALUE are converted to +Infinity.
- Positive numbers smaller than Number.MIN_VALUE and converted to +0.
- Negative numbers greater than -Number.MAX_VALUE are converted to -Infinity.
- Negative numbers smaller than -Number.MIN_VALUE and converted to -0.

### BigInt

Use BigInt when you need to safely store integers outside the range allowed in a Number type.

### String

Represents textual data in 16 bit unsigned integers.
Strings are immutable.

### Symbol

Use as the key of object properties to guarantee uniqueness from other code.

## Objects

Objects are the only mutable values in JavaScript. Objects are a collection of properties which can be added and removed and their values changed.

Objects can be used as a hash map to store and look up values with O(1) speed. As long as the key is calculatable, you can access the value instantly.

Object can be created three ways;

1. Just create it manually

```js
const myObject = { name: "James" };
```

2. Using a constructor function

```js
function Person(name) {
  this.name = name;
}

const myObject = new Person("James");
```

3. Using the Object.create() function

This allows you to pass a prototype that you want to use for the new instances.

## Dates

Use the Date object to store date and time values.

## Arrays

Arrays has many built in functions to work with the data inside.

- find()
- some()
- every()
- filter()
- reduce()
- map()

Underneath, Arrays are just objects with integer numbers as the keys;

```js
const myArray = {
  0: "zero",
  1: "one",
  2: "two",
  3: "three",
};

const two = myArray[2];
console.log(two); // outputs 'two'
```

## Type coercison

Rules for converting one type to another;

- with `+`, if one is a String then both are converted to Strings and added together otherwise numeric addition is performed.
- with `==`, if one is a primative type while the other is an object, then the object is coverted to a primative before doing equality comparison.

## Typeof operator

The `typeof` operator returns a string representation indicating the type of the parameter.

```js
console.log(typeof 42); // outputs "number"
```
