# Website

This website is built using [Docusaurus](https://docusaurus.io/), a modern static website generator.

## Installation

```bash
yarn
```

## Local Development

```bash
yarn start
```

This command starts a local development server and opens up a browser window. Most changes are reflected live without having to restart the server.

## Build

```bash
yarn build
```

This command generates static content into the `build` directory and can be served using any static contents hosting service.

## Deployment

Using SSH:

```bash
USE_SSH=true yarn deploy
```

Not using SSH:

```bash
GIT_USER=<Your GitHub username> yarn deploy
```


If you are using GitHub pages for hosting, this command is a convenient way to build the website and push to the `gh-pages` branch.


for changes

# 1) Create and switch to a new branch
git switch -c feature/my-change[]
# (older Git: git checkout -b feature/my-change)

# 2) Make your edits in the files...
#    then check what changed (optional):
git status
git diff

# 3) Stage everything you changed
git add .

# 4) Create a commit
git commit -m "Describe the change briefly (imperative mood)"

# 5) Push THIS branch to origin (using your current HEAD)
git push -u origin HEAD
# (next pushes can just be: git push)
