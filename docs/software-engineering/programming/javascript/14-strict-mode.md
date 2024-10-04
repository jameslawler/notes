# Strict Mode

[Strict mode](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Strict_mode) is JavaScript is not always available in all browser engines, but the aim is to reduce mistakes.

Advantages;

- Eliminates some JavaScript silent errors by changing them to throw errors.
- Fixes mistakes that make it difficult for JavaScript engines to perform optimizations: strict mode code can sometimes run faster than identical code that’s not strict mode.
- Prohibits some syntax likely to be defined in future versions of ECMAScript.

## Entering strict mode

Add `"use strict"` before any JavaScript code to run it in strict mode.

```js
// Whole-script strict mode syntax
"use strict";
const v = "Hi! I'm a strict mode script!";
```

Example of partial strict mode

```js
function myStrictFunction() {
  // Function-level strict mode syntax
  "use strict";

  function nested() {
    return "And so am I!";
  }

  return `Hi! I'm a strict mode function! ${nested()}`;
}

function myNotStrictFunction() {
  return "I'm not strict.";
}
```
