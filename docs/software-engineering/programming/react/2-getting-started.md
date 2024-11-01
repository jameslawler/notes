# Getting Started

Create React App is deprecated, and instead it is preferrable to use [Vite](https://vite.dev/) to create a new application from scratch.

## Create a project

Use the latest vite package to create a new project using built-in templates using this command - `npm create vite@latest`.

Provide a project name, choose a library (react), and TypeScript.

## Adding TailwindCSS

[TailwindCSS](https://tailwindcss.com/) is a library to provide atomic css classes.

To install TailwindCSS use the following commands.

1. Install packages

`npm install -D tailwindcss postcss autoprefixer`

2. Setup TailwindCSS config

`npx tailwindcss init`

3. Setup tailwindcss.config.js

```js
/** @type {import('tailwindcss').Config} */
export default {
  content: ["./index.html", "./src/**/*.{js,ts,jsx,tsx}"],
  theme: {
    extend: {},
  },
  plugins: [],
};
```

4. Setup postcss.config.js

```js
module.exports = {
  plugins: [require("tailwindcss"), require("autoprefixer")],
};
```

5. Import TailwindCSS in main css file

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

## Start the React server using Vite

Run the following command to start a development server and hot-reload - `npm run dev`
