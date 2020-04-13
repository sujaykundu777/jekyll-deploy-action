# jekyll-deploy
A Github Action to build and deploy Jekyll site to Github Pages

The Action will build a production build of your jekyll site in gh-pages branch on every push.

### Example usage

Put the following inside **yourproject/.github/workflows/main.yml**

```yml
name: jekyll deploy

on:
  push:
    branches:
      - master

jobs:
  build:
    name: deploy
    runs-on: ubuntu-18.04
    steps:
      - name: checkout repo
        uses: actions/checkout@v2
        with:
          ref: 'master'
      - name: Build & Deploy to GitHub Pages
        uses: actions/jekyll-deploy-action@v1
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
          GITHUB_REPOSITORY: ${{ secrets.GITHUB_REPOSITORY }}
          GITHUB_ACTOR: ${{ secrets.GITHUB_ACTOR }}
```
