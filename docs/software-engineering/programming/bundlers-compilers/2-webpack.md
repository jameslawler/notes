# Webpack

## Concepts

[Webpack](https://webpack.js.org/) is a static module bundler for JavaScript applications. Webpack internally builds a dependency graph from the entry point and then combines every module the project needs into one or more bundles which serve your content.

Webpack has the following core concepts

### Entry

The **entry** property indicates where Webpack should start to build its dependency graph. Webpack will crawl through the code and find all dependencies that the entry points needs and keep going down the tree.

Default value `./src/index.js`

A custom entry can be configured by setting the **webpack.config.js**

```js
module.exports = {
  entry: "./path/to/my/entry/file.js",
};
```

### Output

The **output** property tells Webpack where it should save the bundles it creates.

Default value `./dist/main.js` for the main JavaScript bundle and `./dist` for storing other bundled files.

A custom output can be configured by setting the **webpack.config.js**

```js
const path = require("path");

module.exports = {
  entry: "./path/to/my/entry/file.js",
  output: {
    path: path.resolve(__dirname, "dist"),
    filename: "my-first-webpack.bundle.js",
  },
};
```

### Loaders

By default Webpack only knows about JavaScript and JSON files. Loaders allow Webpack to handle other files types (eg. css). Loaders convert other files types into modules that can be consumed by the application and added to the dependency graph.

Using a loader requires to properties `test` and `use`.

- The test property identifies which file should be passed to the loader
- The use property identifies the loader to use for those files

Example:

```js
const path = require("path");

module.exports = {
  output: {
    filename: "my-first-webpack.bundle.js",
  },
  module: {
    rules: [{ test: /\.txt$/, use: "raw-loader" }],
  },
};
```

The rules array is process top to bottom for each file to determine which loader to use.

### Plugins

[Plugins](https://webpack.js.org/plugins) can be used to perform a wider range of tasks that a simple loader. For tasks like bundle optimizations, asset management, and injection of environment variables.

Example:

```js
const HtmlWebpackPlugin = require("html-webpack-plugin");
const webpack = require("webpack"); //to access built-in plugins

module.exports = {
  module: {
    rules: [{ test: /\.txt$/, use: "raw-loader" }],
  },
  plugins: [new HtmlWebpackPlugin({ template: "./src/index.html" })],
};
```

### Mode

The mode property is used to tell Webpack if it should bundle with extra optimizations. The valid options are;

- production
- development
- none

### Browser Compatability

Webpack supports all browsers that are ES5 compliant.

## Basic bundle

### Dependencies

Webpack needs the following

```js
npm install webpack webpack-cli -D
```

### HTML output file in dist folder

To make Webpack automatically generate an index.html file which uses the generated bundle, the plugin `html-webpack-plugin` is available.

```js
npm install html-webpack-plugin -D
```

### Developer web server

To get hot reloading and a self hosted web server for your project, use the `webpack-dev-server`.

```js
npm install webpack-dev-server -D
```

```js
const HtmlWebpackPlugin = require("html-webpack-plugin");
const path = require("path");

module.exports = {
  plugins: [new HtmlWebpackPlugin()],
  mode: "development",
  output: {
    clean: true,
  },
  devServer: {
    contentBase: "./dist",
    open: true,
  },
};
```

## Loaders

Loaders in Webpack are used to convert file types to be a JavaScript module that can be used within a projects.

### CSS

CSS can be loaded with `style-loader` and `css-loader`.

```js
module.exports = {
  module: {
    rules: [
      {
        test: /\.css$/i,
        use: ["style-loader", "css-loader"],
      },
    ],
  },
};
```

Note: The loaders are evaluated from right to left, so `css-loader` first and then `style-loader`.

```css
body {
  background: green;
}
```

```js
import "./style.css";
```

The loader is only used when Webpack adds the file to its dependency graph. So just having a css file in the project is not enough, it needs to be imported somewhere in the project, like with the line above.

These css loaders will take the css from the files and inject them into the <style> tag of the html page.

### SASS / LESS

Both [SASS](https://sass-lang.com/) and [LESS](https://lesscss.org/) are css extensions to css, and so to work with Webpack a loader is needed. Once the SASS / LESS has been converted back to css it can then be procesed the same as css.

SASS:

```js
module.exports = {
  module: {
    rules: [
      {
        test: /\.s[ac]ss$/i,
        use: ["style-loader", "css-loader", "sass-loader"],
      },
    ],
  },
};
```

LESS:

```js
module.exports = {
  module: {
    rules: [
      {
        test: /\.s[ac]ss$/i,
        use: ["style-loader", "css-loader", "less-loader"],
      },
    ],
  },
};
```

### Babel

Babel is used to transpile ES6+ JavaScript to work with older browser that don't support ES6.

```js
module: {
  rules: [
    {
      test: /\.(?:js|mjs|cjs)$/,
      exclude: /node_modules/,
      use: {
        loader: "babel-loader",
        options: {
          targets: "defaults",
          presets: [["@babel/preset-env"]],
        },
      },
    },
  ];
}
```
