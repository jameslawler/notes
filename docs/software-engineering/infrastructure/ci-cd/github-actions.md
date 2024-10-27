---
sidebar_position: 1
---

# Github Actions

[GitHub Actions](https://github.com/features/actions) are a build and deployment CI/CD tool provided for GitHub repositories. GitHub actions are very flexible and allow building / testing of projects in different environments or even within Docker containers.

## Workflows

GitHub Actions use workflow yaml files to define the automation.

### Events

Workflows can be triggered by different events (eg. pushing to a branch, raising an issue, creation of a pull request).

In this example, the workflow is triggered on a push to the main branch of a repository.

```yaml
on:
  push:
    branches:
      - main
```

### Jobs and Steps

A workflow is made up of one or more jobs. Each job performs different steps (eg build command, test command)

An example job which does a checkout of the repository, runs the npm ci and build commands, uploads the "build" folder to the GitHub Pages branch and deploys it to GitHub Pages.

```yaml
jobs:
  build-and-deploy:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v3
      - name: Install and Build
        run: |
          npm ci
          npm run build
      - name: Setup Pages
        uses: actions/configure-pages@v3
      - name: Upload artifact
        uses: actions/upload-pages-artifact@v2
        with:
          path: "build"
      - name: Deploy to GitHub Pages 🚀
        id: deployment
        uses: actions/deploy-pages@v2
```
