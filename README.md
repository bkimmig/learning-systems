# Learning Systems


Powered by [Hugo](https://github.com/gohugoio/hugo).

# Developing

All the code is kept in this repository. The code for generating the content is
kept on the `source` branch with a github action that pushes the generated site
to the `main` branch.

## Adding themes

Currently using the Etch theme...

`git submodule add https://github.com/LukasJoswiak/etch.git themes/etch`

## Steps to develop

Install `hugo` (on mac `brew install hugo`)

- `git clone --recurse-submodules <repo location>`
    + The `--recurse-submodules` is required to install the specified hugo theme.
    + If the repo is already cloned, run `git submodule update --init --recursive` to achive the same effect.
- `git checkout source`
- `git checkout -b "your branch"`
- add code
    + a blog post should go in the `content/posts` directory - this can be done with `hugo new posts/{name of your post}.md`
- view it locally with `hugo serve`
- pull request into source
- merge
- the github action will build and push the code to `main`

## Useful links

- Site is available at: https://bkimmig.github.io/learning-systems/

