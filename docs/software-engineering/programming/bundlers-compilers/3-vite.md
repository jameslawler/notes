# Vite

Vite (said as veet), is a modern bundler that aims to make development more efficient by keeping ES Modules for development mode, but using a bundler for production mode.

## Development mode

During development, Vite uses ESBuild which is a tool written in Go and is 10-100x faster than other bundlers. Vite serves the source code over native EMS so the browser does the job of bundling. Vite bundles on demand as the code is requested.

## Production mode

During production mode, Vite still pre-bundles so that the build can be optimized with tree-shaking, lazy loading, and chunk splitting. Pure ES Modules are not ready for production use as when they are not bundled, the browser needs to make more network round trips caused by nested imports.

Vite uses [rollupjs](https://rollupjs.org/) for bundling in production.
