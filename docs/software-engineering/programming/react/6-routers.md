# Routers

Routers are used to integrate page navigation within a project. Url to Component mappings can be defined as well as the dynamic parts of a url.

## React-Router

[React Router](https://reactrouter.com/en/main) is a library that allows client side routing in React applications. The library is able to updaet the browser url and history without making a call to the server side.

Routes are defined by url paths and then a component is loaded based on the path.

Example React Router that defines two paths and two components.

```jsx
import * as React from "react";
import { createRoot } from "react-dom/client";
import {
  createBrowserRouter,
  RouterProvider,
  Route,
  Link,
} from "react-router-dom";

const router = createBrowserRouter([
  {
    path: "/",
    element: (
      <div>
        <h1>Hello World</h1>
        <Link to="about">About Us</Link>
      </div>
    ),
  },
  {
    path: "about",
    element: <div>About</div>,
  },
]);

createRoot(document.getElementById("root")).render(
  <RouterProvider router={router} />
);
```

### Dynamic segments

Urls can contain dynamic parts which allows the passing of data to routes.

Define a route path and use `:` to specify the dnyamic parameters.

```jsx
<Route path="projects/:projectId/tasks/:taskId" />
```

`projectId` and `taskId` are dynamic.

From within the loaded component, the parameters can be accessed using the `useParams` function.

```jsx
// eg loaded url /projects/abc/tasks/3

function Task() {
  const params = useParams();
  params.projectId; // abc
  params.taskId; // 3
}
```
