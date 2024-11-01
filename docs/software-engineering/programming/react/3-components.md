# Components

Components are reusable UI components. In React everything is a components, including pages.

## Props

Props are a way to pass parameters into components. A prop can be one way or two way. For example, passing in a string will allow the component to use the string (eg display it). Passing in a function will allow the component to interact with the parent of the component (eg on a button click the parent component can perform an action).

In TypeScript, props are defined simply by providing parameters with a type definition.

```jsx
import { ImagePayload } from "../types/message";

function ContentImage({ payload }: { payload: ImagePayload }) {
  return (
    <div className="w-44 md:w-80">
      <img src={payload.imageBase64} />
      <div className="text-sm text-center">{payload.imageAltText}</div>
    </div>
  );
}

export default ContentImage;
```

In this examle component, `payload` parameter is a one way prop of type ImagePayload.

## Use a component

In a parent component or page you can integrate a component by importing it and then using it.

```jsx
import { ContentImage } from "./components/ContentImage";

function Page() {
  return (
    <div>
      <ContentImage payload="..." />
    </div>
  );
}
```
