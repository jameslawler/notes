# Hooks

Some hooks are built-in and you can also create your own

## State Hook

To be able to set and read state that persists between re-renders, you can use the `useState` hook.

```jsx
const [index, setIndex] = useState(0);
```

The parameter passed in to the `useState` is the initial state.

## Effect Hook

To be able to react to state changes the `useEffect` hook listens for changes and then can execute code to changes. Effect hooks are typically used for interacting with external systems outside of the React environment (eg. fetch api calls).

```jsx
useEffect(() => {
  // do something
}, [inputName]);
```

If an anonymous function is returned from a `useEffect` it is used like a deconstructor and is executed when the component is unloaded.

```jsx
useEffect(() => {
  // do something
  return () => disconnect();
}, [inputName]);
```

## Ref Hook

Ref hooks are used to interact with the DOM nodes or other things like timeouts.

```jsx
function Page() {
  const messagesRef = useRef < HTMLDivElement > null;

  return (
    <div>
      <div ref={messageRef}>Hello</div>
    </div>
  );
}
```
