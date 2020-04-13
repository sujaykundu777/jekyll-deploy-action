# jekyll-deploy
A Github Action to build and deploy Jekyll site to Github Pages

The Action will build a production build of your jekyll site in gh-pages branch on every push.

### Example usage

Put the following inside **yourproject/.github/workflows/main.yml**

```yml
name: Jekyll Deploy

on:
  push:
    branches: [ master ]
  pull_request:
    branches: [ master ]

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v2
    - name: Deploy Jekyll Site
      uses: sujaykundu777/jekyll-deploy-action@v1
      env:
        GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
        GITHUB_REPOSITORY: ${{ secrets.GITHUB_REPOSITORY }}
        GITHUB_ACTOR: ${{ secrets.GITHUB_ACTOR }}

```
