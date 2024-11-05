# State Management

React provides many possibilities for state management.

## Component level

To maintain state within a single component (and children), use the `useState` hook. The state is persisted through renders and is immutable.

## Application level

Persisting state beyond a component and to the entire application can be done using different approaches.

### Context

The [useContext hook](https://react.dev/reference/react/useContext) is a built-in hook in React that allows you to consume data from a context provider. A context provider is a component that provides data to all of its children via a context object. The React useContext hook allows you to access this context object and retrieve the necessary data.

An example context with state inside.

```jsx
import React, { useState, useContext } from "react";

const ThemeContext = React.createContext();

function ThemeProvider(props) {
  const [theme, setTheme] = useState("light");

  const toggleTheme = () => {
    setTheme(theme === "light" ? "dark" : "light");
  };

  return (
    <ThemeContext.Provider value={{ theme, toggleTheme }}>
      {props.children}
    </ThemeContext.Provider>
  );
}

function App() {
  const { theme, toggleTheme } = useContext(ThemeContext);

  return (
    <div className={`app ${theme}`}>
      <button onClick={toggleTheme}>Toggle Theme</button>
    </div>
  );
}

export default App;
```

### Zustand

[Zustand](https://github.com/pmndrs/zustand) is an alternative to the heavy Redux state management library.

Hook based state managements

```jsx
import { create } from "zustand";

const useBearStore = create((set) => ({
  bears: 0,
  increasePopulation: () => set((state) => ({ bears: state.bears + 1 })),
  removeAllBears: () => set({ bears: 0 }),
}));
```

Use the state in a component

```jsx
function BearCounter() {
  const bears = useBearStore((state) => state.bears);
  return <h1>{bears} around here ...</h1>;
}

function Controls() {
  const increasePopulation = useBearStore((state) => state.increasePopulation);
  return <button onClick={increasePopulation}>one up</button>;
}
```

### Redux

[Redux](https://redux.js.org/) is the original state management for React, but less frequently used now.
