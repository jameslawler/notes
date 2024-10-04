# Asynchronous

In order to perform long running tasks `asynchronous` programming is used. As JavaScript is single-threaded any long running task by default with block the main thread.

## Event handlers

Event handlers are a form of asynchronous programming, you provide a function to call when back when an event occurs.

## Callbacks

An event handler is a type of callback. A callback is just another function that is passed to another function.

## Promises

A promise is a function that is returned by an asynchronous function after being called. The promise keeps track of the current state of the asynchronous function.

Promises expose two methods that will be called based on the outcome.

- then() -> called when the promise finishes.
- catch() -> called when an error occurs.

### Terminology

There are three states of a promise

- pending - the promise has been created and is in a running state
- fulfulled - the promise has succeeded
- rejected - the promise has failed

## Async / Await

The `async` and `await` keywords are a simpler way to work with promises.

A function must be defined as `async` in order to be able to run asynchronously.

In side the `async` function you can use the `await` keyword before calling a function that returns a promise. The `await` keyword makes the program execution wait there until the promise is fulfilled or rejected.

```js
const slowCall = async () => {
  const result = await fetch();
  return result;
};

slowCall()
  .then((result) => console.log(result))
  .catch((error) => console.error(error));
```

## Background tasks

### setTimeout

The setTimeout function runs a function after a specific amount of time has passed.

```js
const slowHello = () => setTimeout(() => console.log("Hello"), 1500);

sayHello(); // will output "hello" after 1.5 seconds
```

### setInterval

The setInterval function is similar to `setTimeout` except it doesn't only run once, it executes repeatedly on an interval.

```js
const sayHelloEverySecond = () => setInterval(() => console.log("hello"), 1000);

setHelloEverySecond(); // will output "hello" every 1 second
```

### Cancelling timeouts and intervals

To cancel a timeout or interval the `clearTimeout` or `clearInterval` can be used.

The result of the `setTimeout` or `setInterval` call returns an id that can be used to cancel.

```js
let timerId = setTimeout(...);
clearTimeout(timerId);
```

```js
let timerId = setInterval(...);
clearInterval(timerId);
```
