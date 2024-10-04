# Functions

Functions are the core piece of all programming langauges and provide a way to reuse code.

## Defining functions

In JavaScript you can define functions in multiple ways.

A named function:

```js
function addNumbers(a, b) {
  return a + b;
}

console.log(addNumbers(4, 5)); // outputs 9
```

An anonymous function that is assigned to a variable:

```js
const addNumbers = function (a, b) {
  return a + b;
};

console.log(addNumbers(4, 5)); // outputs 9
```

## Function hoisting

Like variable hoisting, JavaScript will move a function to the top of the code file so that it is alwasy available no matter where it is executed from within the same file.

```js
console.log(addNumbers(4, 5)); // outputs 9

function addNumbers(a, b) {
  return a + b;
}
```

During the Just in Time compilation, the function is moved to the top to look like this.

```js
function addNumbers(a, b) {
  return a + b;
}

console.log(addNumbers(4, 5)); // outputs 9
```

Function hoisting does not work when functions are assigned to variables.

## Scope

Variables defined within a function are only accessible within the same function.

## Closures

In JavaScript functions can be defined within other function and provide a technique for sharing scope from the outer function to the inner function even beyond the life of the outer function.

Example;

```js
// The outer function defines a variable called "name"
const pet = function (name) {
  const getName = function () {
    // The inner function has access to the "name" variable of the outer function
    return name;
  };
  return getName; // Return the inner function, thereby exposing it to outer scopes
};
const myPet = pet("Vivie");

console.log(myPet()); // "Vivie" is returned even though the pet() function has finished executing.
```

## Default parameters

By default parameters in JavaScript are `undefined`. This can be overriden within the function definition by passing a default parameter value.

```js
function addNumbers(a, b = 5) {
  return a + b;
}

console.log(addNumbers(4)); // outputs 9
```

## Rest parameters

Rest parameters allow an unlimited number of parameters to be passed to a function and are stored in an array.

```js
function multiply(multiplier, ...theArgs) {
  return theArgs.map((x) => multiplier * x);
}

const arr = multiply(2, 1, 2, 3);
console.log(arr); // [2, 4, 6]
```

## Arrow functions

Arrow functions are a shorthand for creating anonymous functions.

```js
const a = ["Hydrogen", "Helium", "Lithium", "Beryllium"];

// without using arrow function
const a2 = a.map(function (s) {
  return s.length;
});

console.log(a2); // [8, 6, 7, 9]

// easier to read with arrow function
const a3 = a.map((s) => s.length);

console.log(a3); // [8, 6, 7, 9]
```

## IIFE

Immediately Invoked Function Expressions is what IIFE stands for.

```js
(() => {
  // do stuff
})();
```

Can only be executed once and it is executed immediately upon creation.

Usages:

- To not pollute the global namespace as the function is isolated.
- To replicate the concept of a module/class in pre ES6 days. A function can have internal variables and then expose functions back.

```js
const Person = (() => {
  let name;
  let age;

  return {
    setName: (newName) => (name = newName),
    getName: () => name,
    setAge: (newAge) => (age = newAge),
    getAge: () => age,
  };
})();

Person.setName("James");
Person.setAge(30);
console.log(`Name: ${Person.getName()} with Age: ${Person.getAge()}`);
```

## Parameter arguments

A function in JavaScript exposes an `arguments` array which provides access to all arguments of that function without using their names.

```js
function addNumbers(a, b) {
  return arguments[0] + arguments[1];
}

console.log(addNumbers(4, 5)); // outputs 9
```
