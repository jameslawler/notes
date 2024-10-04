# Classes

Classes are a template for creating objects and are built on `prototypes`.

```js
class MyClass {
  constructor() {}
  method1() {}
}
```

Instances are created by using the `new` keyword.

```js
const aClass = new MyClass();
```

Classes automatically use the prototype to store functions.

## Class expressions

Classes, like functions, can be passed around to function calls and in variables. This is done by assigning the class to a variable.

```js
let User = class {
  sayHi() {
    alert("Hello");
  }
};
```

## Getters and Setters

Classes can have getters and setters defined.

```js
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  get nameAndAge() {
    return `${this.name} is ${this.age} years old`;
  }
}

const bob = new Person("bob", 25);

console.log(bob.nameAndAge); // outputs "bob is 25 years old"
```

## Inheritance

Inheritance can be implemented in JavaScript through the use of the `extends` keyword.

```js
class Animal {
  constructor(name) {
    this.name = name;
  }

  speak() {
    console.log(`${this.name} makes a noise.`);
  }
}

class Dog extends Animal {
  constructor(name) {
    super(name); // call the super class constructor and pass in the name parameter
  }

  speak() {
    console.log(`${this.name} barks.`);
  }
}

const d = new Dog("Mitzie");
d.speak(); // Mitzie barks.
```
