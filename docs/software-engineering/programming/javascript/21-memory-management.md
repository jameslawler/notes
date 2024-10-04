# Memory management

In JavaScript memory management and garbage collection is done automatically based on if a reference is still reachable by the code.

Example of non reachable variable that will be garbage collected.

```js
let user = {
  name: "John",
};

user = null;
```

Example of a reachable variable that will be kept in memory.

```js
let user = {
  name: "John",
};

let admin = user;
user = null;
```
