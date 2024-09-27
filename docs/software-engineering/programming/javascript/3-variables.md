# Variables

## Declaring variables

There are three keywords to be able to declare a variable

- let
- const
- var

### Let

The `let` keyword is used to create a variable that can be changed.

### Const

The `const` keyword is used to create a variable that can not be changed.

### Var

The `var` keyword is used to store any type of variables, but is now deprecated and `let` and `const` should be used instead as these are more specific if they are dynamic aor static.

## Initializing a variable

This is done by assigning a value to the variable

```js
let name = "James";
```

or

```js
let name;
name = "James";
```

## Hoisting

Varaibles that are declared using the `var` or `function` keywords are automatically moved to the top of the script, no matter where they are declared in the code. This does not apply to `const` and `let` keywords.

```js
console.log(name);
name = "James";
var name;
```

is the same as

```js
var name;
console.log(name);
name = "James";
```

Note: When the variable declartion is hoisted, it is set to `undefined`, so in this example the console.log would output `undefined`.

## Variable Scope

Variable scope refers to who can access a variable based on where it is declared.

- Global
- Module
- Function
