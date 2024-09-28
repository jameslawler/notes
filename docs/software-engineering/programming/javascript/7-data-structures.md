# Data Structures

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

## Indxed collections

These are Array and TypedArray objects.

### Array

Three ways to create an array;

- const arr1 = new Array(1, 2, 3, 4, 5);
- const arr2 = Array(1, 2, 3, 4, 5);
- const arr3 = [1, 2, 3, 4, 5];

You can also create an array using the first two functions above, but instead of passing elements, you pass the size of the array.

eg. `const arr4 = new Array(5);` will create an array of length 5 without any items inside.

Access the length through;

```js
const length = arr1.length;
```

### TypedArray

(MDN)[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Typed_arrays]
