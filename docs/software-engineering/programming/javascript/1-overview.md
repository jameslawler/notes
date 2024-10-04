# Overview

JavaScript is a lightweight interpreted programming language. The most common usage of JavaScript is wihin web browsers to provide client side scripting for static HTML web pages.

These notes follow the structure from the [JavaScript roadmap](https://roadmap.sh/javascript)

The language has the following features

- just in time compiled
- first-class functions
- prototype-based
- multi-paradigm
- single-threaded
- dynamic language

JavaScript supports

- object-oriented
- imperative
- declarative style

## Just in Time (JIT) compiled

This means that the code is compiled at run time as it is executed. The benefit of a just in time compiler is that it observes the program as it is running and can make optimizations to the machine level code.

- Chrome uses the V8 JIT compiler
- FireFox uses the SpiderMonkey / IonMonkey JIT compiler.
- pypy is the python JIT compiler. Standard python runs using a pre compiled compiler.

[Video](https://www.youtube.com/watch?v=d7KHAVaX_Rs)

## First-class functions

A first-class function is one where a function is treated as a variable and can be passed around as a parameter, returned, or reassigned.

```js title="Example first class functions
const foo = () => {
  console.log("foobar");
};
foo(); // Invoke it using the variable
```

In this example, `foo` is the variable which has been assigned an anonymous function `() => {}`. The code then execute the anonymous function by calling the variable foo with parenthesis `foo()`.

## Prototype-based

Classes are not explicitly defined but rather properties and functions are addedto a class or object.

When you define a new object and you inspect in the browser you will see this variable `__proto__`. This is a pointer to the protoype of the object. Prototypes are shared between all instances of the class and it also allows features like inheritance.

[Video](https://www.youtube.com/watch?v=4jb4AYEyhRc)

## Multi-paradigm

This means that you can use JavaScirpt to write code in various different styles.

- procedural
- object oriented
- functional

## Single-threaded

Due to the environment in which JavaScript was born, it was intended to only run in browsers and to work on slower computers, it was chosen to be a single threaded langauge.

OVer time as JavaScript became more widely used, techniques were invented to get around the single threaded nature of JS when you want to run long running tasks.

- callbacks
- promises
- async/await

## Dynamic language

The JIT compiler only assigned variables a type at run time once it holds a value.
