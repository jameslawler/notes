# Control Flow

## If ... else

Classic flow control if statement

```js
if (condition) {
  statement1;
} else {
  statement2;
}
```

## Switch statement

Switch statements work in JavaScript like most other programming languages, but they should be avoided for readbility reasons.

```js
switch (expression) {
  case value1:
    //Statements executed when the result of expression matches value1
    break;
  case value2:
    //Statements executed when the result of expression matches value2
    break;
  ...
  case valueN:
    //Statements executed when the result of expression matches valueN
    break;
  default:
    //Statements executed when none of the values match the value of the expression
    break;
}
```

An alternative is to use an object to execute based on values.

```js
const conditions = {
  first: () => doSomething(),
  second: () => doSomething(),
  third: () => doSomething(),
};

const output = conditions[value]();
```

## Truthy

Truthy is a term in JavaScript to mean that a value evaluates to be a truth. So not just booleans can be true, but any value. For example the value 0 is false and anything other than 0 means true, or "hello" is true but "" is false.

A truthy evaluation can be converted to a boolean by doing a double negation.

`!!"hello"` // equals true

The first negation `!` converts the truthy into a boolean in its negative form. So the negation of "hello" is false. Then you apply a second negation `!` to convert it to the actual boolean representation of true.

## ? Operator

The `?` can be used as a shorthand to do a assignment ternary.

`const ageAccess = age > 18 ? "over 18" : "under 18";`

`age > 18` is evaluated and if the result is true then the first part after the `?` is returned and assigned to the `ageAccess` variable, otherwise the second part is returned.

## Exceptions

Exceptions in JavaScript are just objects that are returned.

You can use the build in `Error` object or create a customer `Error` object.

```js
throw new Error("Exception message");
```

```js
function CustomException(message) {
  const error = new Error(message);

  error.code = "THIS_IS_A_CUSTOM_ERROR_CODE";
  return error;
}

throw new CustomException("Exception message");
```

Exceptions are caught by a try...catch

```js
// Caught errors
try {
  doSomething();
} catch (e) {
  console.log("Something went wrong", e);
}
```

If you create multiple custom exception error objects then you can determine the type of error that has occurred by checking which instance the error is.

```js
try {
  willGiveErrorSometime();
} catch (error) {
  if (error instanceof RangeError) {
    rangeErrorHandler(error);
  } else if (error instanceof ReferenceError) {
    referenceErrorHandle(error);
  } else {
    errorHandler(error);
  }
}
```
