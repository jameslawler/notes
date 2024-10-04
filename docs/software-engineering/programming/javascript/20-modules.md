# Modules

Modules are used to split up logic in an application. A module is just a file in JavaScript.

Modules can be imported and exported using the keywords `import` and `export`.

## CommonJS

CommonJS is the default for Node.js. By using CommonJS, modules are exported using `module.exports = function() {}` and imported using the require syntax `const {add} = require('./script')`;

```js
module.exports.add = function(a, b) {
  return a + b;
}

module.exports.subtract = function(a, b) {
  return a - b;
}

----

const {add, subtract} = require('./util')

console.log(add(5, 5)) // 10
console.log(subtract(10, 5)) // 5
```

## ES Modules (ECMAScript 2015 / ES6)

With ES6, import and export statements were added to allow more efficient tree-shaking builds and support fro==or both static and dynamic imports.

```js
export const add = (x, y) => x + y;
export const subtract = (x, y) => x - y;

----

import { add } from './math.js';
console.log(add(2, 3)); // Output: 5
```

## Default vs Named Import

### CommonJS

```js
module.exports.namedFunction = function () {};
module.exports = { namedFunction };

----

const defaultFunction = require('./');
defaultFunction.namedFunction();

or

const { namedFunction } = require('./');
namedFunction();
```

### ES Modules

```js
export const namedFunction = () => {}
export default function() => {}

----

import { namedFunction } from './';
namedFunction();

import defaultFunction from './';
defaultFunction();

import * as allNamedFunctions from './';
allNamedFunction.namedFunction();
```

## Differences

| Feature        | require                                                           | import                                                                                  |
| -------------- | ----------------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| Module System  | CommonJS                                                          | ES6 (ECMAScript version 6)                                                              |
| Loading Type   | Synchronous (modules are imported sequentially)                   | Mostly static (modules are loaded in order at compile time, dynamic import is async)    |
| Performance    | Less efficient due to synchronous loading                         | More efficient with static imports due to predictability and async with dynamic imports |
| Memory Usage   | Imports entire module, leading to potentially higher memory usage | Can import selective components, reducing memory usage                                  |
| Export Access  | Access to components exported by module.exports                   | Access to components exported by export                                                 |
| Implementation | Can be used directly as it is the default method in Node.js       | Requires ES6 or ECMAScript module support enabled                                       |
| Usage in Code  | Can be used anywhere in the program                               | Static imports are used at the top, dynamic can be used within the program              |
