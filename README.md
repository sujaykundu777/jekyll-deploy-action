# jekyll-deploy
A Github Action to build and deploy Jekyll site to Github Pages

The Action will build a production build of your jekyll site in gh-pages branch on every push. Very helpful, when you want to use jekyll plugins which are not supported by Github Pages Yet.

![Build Screenshot](https://github.com/sujaykundu777/jekyll-deploy-action/blob/master/screenshot.PNG?raw=true)

### Example usage

You need to set build folder as God demands, add the following in your site's **_config.yml** :

```yml
destination: ./build
```

And, put the following inside **yourjekyllsite/.github/workflows/main.yml**

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
      uses: sujaykundu777/jekyll-deploy-action@1.0.2
      env:
        GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
        GITHUB_REPOSITORY: ${{ secrets.GITHUB_REPOSITORY }}
        GITHUB_ACTOR: ${{ secrets.GITHUB_ACTOR }}
```
