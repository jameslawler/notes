# Expressions

## Conditional operators

This is known as the ternary operator

```js
const allowedMessage = age > 18 ? "Allowed" : "Denied";
```

## Comma operators

If you put a comma between expressions they are evaluated left to right and only the last result is the one that is returned.

Typically only used for `for loops`.

```js
for (let i = 0; i < 100; i++) {
  // do stuff
}
```

## Unary operators

These are operations which only have one operand.

For example:

- delete
- typeof

## Relational operators

A relational operator compares the operands and returns a Boolean value based on whether the comparison is true.

### in

Returns true if the specied property is in the specified object

```js
propertyName in objectName;
```

### instanceof

Returns true if the specified object is of the specified object type.

```js
object instanceof objectType;
```

## Assignment operators

Operators to assign one value to another.

- =
- +=
- -=
- \*=
- /=

There are more for bitwise operations and other edge case usages

[MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_operators#assignment_operators)

## Comparison operators

Returns a Boolean based on the comparison of the operands.

- {'=='}
- {'!='}
- {'==='} (strict)
- {'!=='} (strict)
- {'>'}
- {'>='}
- {'<'}
- {'<='}

## Arithmetic operators

To apply mathematical operations to numbers.

- % (modulous)
- ++ (increment by one)
- -- (decrement by one)
- - (minus)
- - (plus)
- \*\* (exponentiation)

## Bitwise operators

Used for manipulating binary values

- a & b
- a | b
- a ^ b
- ~ a
- a {'<<'} b
- a {'>>'} b
- a {'>>>'} b

## Logical operators

Used for combining expressions based on logic.

- && (and)
- || (or)
- ?? (null coalescing - returns expr1 if it is not null or undefined, otherwise returns expr2)
- ! (not)

## BigInt operators

## String operators

Use the `+` operator to concatenate strings and return a new string.

```js
console.log("hello" + "world!");
```
