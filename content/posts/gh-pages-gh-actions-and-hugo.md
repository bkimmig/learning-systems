---
title: "Github Pages, GitHub Actions, and Hugo"
date: 2021-10-24T15:00:00-00:00
authors: ["Brian Kimmig"]
---

For the last few years I've had my personal website hosted via [GitHub
Pages](https://pages.github.com/). To make my life even easier I've always used
a static site generator; first I used [Pelican](https://blog.getpelican.com/)
and most recently had it set up with [Nikola](https://getnikola.com/) - both
were great. Nikola is especially nice as it made deploying Jupyter notebooks as
blog posts incredibly easy.

Recently I've wanted to mess with the style of my site a bit more. Nothing
crazy, but maybe make it more simple or just give myself some other ways to
easily change the look and feel. When searching for other static site tools I
quickly came across [Hugo](https://github.com/gohugoio/hugo) a very popular
static site generator written in `golang` - there are also a ton of
[themes](https://themes.gohugo.io/) already made for it! I should note that I am
a huge fan of `golang` so that gave me even more of a push to use this tool.

Similar to the interface Nikola provides, I wanted all of my source code and the
website code to live in the same repository. Hugo and GitHub actions make this
possible. I'll give a brief overview of the steps below.

My website repository is
[bkimmig.github.io](https://github.com/bkimmig/bkimmig.github.io). You'll notice
that the `main` branch contains only the site code. The other branch to consider
here is called `source` - this contains all of the code to generate the site.
From there, I have a GitHub Action set up to build and push the site to the
`main` branch on any push to the `source` branch.

[This](https://gohugo.io/hosting-and-deployment/hosting-on-github/) is the
tutorial on how to use Hugo in combination with GitHub pages. With a few minor
tweaks you can use this file to push the compiled site Hugo create to the `main`
branch on a push to `source`.

1. Install and get a basic Hugo site going - [Quick Start Guide](https://gohugo.io/getting-started/quick-start/)
1. Create your repository given the [GitHub Pages](https://pages.github.com/) guidelines
1. Set up your hugo static site generating code on the `source` branch of your
   new repository.
1. Under the repository's GitHub Pages settings, select the `main` branch to be
   the source.
1. Create your GitHub Actions workflow directory `mkdir -p github/workflows/ && touch github/workflows/gh_pages.yml`
1. Add the following snippet to `gh_pages.yml`

```yaml
name: github pages

on:
  push:
    branches:
      - source  # Set a branch to deploy

jobs:
  deploy:
    runs-on: ubuntu-18.04
    steps:
      - uses: actions/checkout@v2
        with:
          submodules: true  # Fetch Hugo themes (true OR recursive)
          fetch-depth: 0    # Fetch all history for .GitInfo and .Lastmod

      - name: Setup Hugo
        uses: peaceiris/actions-hugo@v2
        with:
          hugo-version: 'latest'
          # extended: true

      - name: Build
        run: hugo --minify

      - name: Deploy
        uses: peaceiris/actions-gh-pages@v3
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          publish_dir: ./public
          publish_branch: main
```

Now any push to the source branch will build and deploy your site to the main
branch.
