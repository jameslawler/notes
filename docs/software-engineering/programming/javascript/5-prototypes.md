# Prototype

In JavaScript every object inherits properties from its prototype. A prototype is just an object with properties which other objects inherit from.

Instead of adding functions directly into objects you can add them to the prototype of that object. Then when you create instances of that object there exists only one copy of the function on the shared prototype. This saves resources.

## [[Prototype]] attribute

JavaScript uses the internal [[Prototype]] attribute to contain a reference to its prototype. It is possible to create an object with a `null` prototype.

## Define a prototype when creating an object

By using `Object.create()` you can pass the prototype object to the new object.

```js
var a = { x: 10, y: 20 };

// make a as the prototype
var b = Object.create(a);

// add the properties one-by-one
b.p = 100;
b.q = 200;
```

## Prototype chaining

This is an approach in JavaScript to acheive OO type inheritance.

```js
var a = { x: 10, y: 20 };
var b = Object.create(a);
var c = Object.create(b);
```

In this situation `c` object has access to all of the properties in `b` and `a`.

## Property retrieval

If an inherited object has a property with the same name, then the order of preference is as follows;

```js
var o1 = { a: 100, b: 200, c: 300 };
var o2 = { a: 10, b: 20 };
var o3 = { a: 1 };
```

o3.a returns 1; o3.b returns 20; o3.c returns 300;
o2.a returns 10; o2.b returns 20; o2.c returns 300;
o1.a returns 100; o1.b returns 200; o1.c returns 300;

## .prototype property

The `.prototype` property on the constructor function gives us access to the prototype that all instances of the class/function will use.

```js
function Point(x = 0, y = 0) {
  this.x = x;
  this.y = y;
}

Point.prototype.setTo = function (x, y) {
  this.x = x;
  this.y = y;
};
```

The setTo function in this case is not created again and again for each instance of Point, but rather it only exists once on the prototype but is accessible for all instances of Point.

The setTo function also does not use the global scope in any way and so it is only accessible to Point instances.

## Changing the prototype of existing object

You can change the prototype by;

- Assinging a value to the object's `__proto__` property.
- Call the Object.setPrototypeOf() method.
