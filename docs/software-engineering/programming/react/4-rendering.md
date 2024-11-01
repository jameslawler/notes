# Rending

React uses a Virtual DOM which is a light weight in-memory representation of the DOM.

When state changes, the Virtual DOM representation is updated and then it is compared to the current Virtual DOM.

React then updates the real DOM with the minimal changes necessary in order to make it match the Virutal DOM state.
