# Calling APIs

During web development you will likely need to call external apis.

## Fetch

The Fetch api is an async function that returns a promise. The result of the promise will be a `response` object which contains an `ok` boolean, `status` string, and `.json()` function to access the body.

```js
fetch("products.json")
  .then((response) => {
    if (!response.ok) {
      throw new Error(`HTTP error: ${response.status}`);
    }
    return response.json();
  })
  .then((json) => initialize(json))
  .catch((err) => console.error(`Fetch problem: ${err.message}`));
```

## XMLHttpRequest API

The XMLHttpRequest is an older way that predates the `fetch` api. `Fetch` is the preferred way to make API calls in JavaScript.

```js
const request = new XMLHttpRequest();

try {
  request.open("GET", "products.json");

  request.responseType = "json";

  request.addEventListener("load", () => initialize(request.response));
  request.addEventListener("error", () => console.error("XHR error"));

  request.send();
} catch (error) {
  console.error(`XHR error ${request.status}`);
}
```
