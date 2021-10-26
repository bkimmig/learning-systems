# Learning Systems


Powered by [Hugo](https://github.com/gohugoio/hugo).

# Developing

All the code is kept in this repository. The code for generating the content is
kept on the `source` branch with a github action that pushes the generated site
to the `main` branch.

## Steps to develop

Install `hugo` (on mac `brew install hugo`)

- `git checkout source`
- `git checkout -b "your branch"`
- add code
    + a blog post should go in the `content/posts` directory - this can be done with `hugo new posts/{name of your post}.md`
- pull request into source
- merge
- the github action will build and push the code to `main`
