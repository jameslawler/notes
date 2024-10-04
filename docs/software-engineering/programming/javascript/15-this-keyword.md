# This keyword

The this keyword can refer to different things depending on the usage and where it is being used.

- In an object method, `this` refers to the object
- Alone, `this` refers to the global object
- In a function, `this` refers to the global object
- In a function, in strict mode, `this` is undefined
- In an event, `this` refers to the element that received the event
- Methods like call(), apply(), and bind() can refer `this` to any object

## Call

The call method of a `Function` calls the function with a given `this` value.

```js
function Product(name, price) {
  this.name = name;
  this.price = price;
}

function Food(name, price) {
  Product.call(this, name, price);
  this.category = "food";
}

console.log(new Food("cheese", 5).name);
// Expected output: "cheese"
```

## Apply

The apply method of a `Function` is similar to the `call` method except it passes an _array of arguments_.

```js
const numbers = [5, 6, 2, 3, 7];

const max = Math.max.apply(null, numbers);

console.log(max);
// Expected output: 7

const min = Math.min.apply(null, numbers);

console.log(min);
// Expected output: 2
```

## Bind

Bind creates a new function with a specific `this` that can be used later.

```js
const module = {
  x: 42,
  getX: function () {
    return this.x;
  },
};

const unboundGetX = module.getX;
console.log(unboundGetX()); // The function gets invoked at the global scope
// Expected output: undefined

const boundGetX = unboundGetX.bind(module);
console.log(boundGetX());
// Expected output: 42
```
