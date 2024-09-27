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

## Keyed collections

### Maps

There is a Map type which represents key value stored data.

```js
const map1 = new Map();

map1.set("a", 1);
map1.set("b", 2);
map1.set("c", 3);

console.log(map1.get("a"));
```

Historically Objects were used as a Map, but there are some differences;

- Map has no keys by default whereas Object has prototype keys which could collide.
- Map keys are safe for using user provided keys, whereas Object is vulnerable to prototype override injections
- Map keys can be any primative value whereas Object keys can only be String or Symbol types.
- Map keys are ordered by the insertion order whereas Object keys are not guaranteed to have the same order.
- Size of the map can be retrieved from the Size property whereas Object size needs to first get the Object.keys() and then call length.
- Maps are iteratable whereas Objects are not as you must use for..of or Object.entries() to be able to iterate.
- Maps are more performant as they are optimized key value stores.
- Maps are not serializable by default whereas Objects can be by using JSON.stringify().

### Sets

Sets are collections of data that keep unique values. You can not have the same value in a set more than once.

Sets are;

- Iteratable
- Ordered by insertion order
- Lookup complexity is always less than O(N)
- Set .has method is more performant than Array.includes

Sets can be composed together to find unions, differences, intersections etc.

- A.difference(B) will return values that are in A but not B.
- A.intersection(B) will return values that are in A and B.
- A.symmetricDifference(B) will return values that are not in A and B.
- A.union(B) will return a new Set with unique values in A and B.
- A.isDisjointFrom(B) will return a Boolean true or false if any of the values in A intersect with values from B. True mean no values intersect, false means some intersect.
- A.isSubsetOf(B) will return true if all values of A exists in B.
- A.isSupersetOf(B) will return true if all values of B exist in A.

These functions can also be used with Set like types (eg Map)

## Structured data - JSON

JSON is a data format in JavaScript which is object and array based. Think of it as an alternative to XML.

Used for data storage and data transfer.

## Type coercison

Rules for converting one type to another;

- with `+`, if one is a String then both are converted to Strings and added together otherwise numeric addition is performed.
- with `==`, if one is a primative type while the other is an object, then the object is coverted to a primative before doing equality comparison.
