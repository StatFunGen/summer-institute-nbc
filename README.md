# StatFunGen Summer Institute NBC

This repository contains a Hugo site using the Hugo Book theme.

Markdown source files live in `content/docs/`. The generated static HTML files
are written to `public/` by GitHub Actions and committed back to this repository.
This repository does not use a GitHub Pages deployment workflow.

## Editing Content

Add or edit Markdown under `content/docs/`, then push to `main`.

```text
content/docs/
  _index.md
  about.md
  lectures/
  practicals/
```

The workflow in `.github/workflows/build-html.yml` runs Hugo, writes the site to
`public/`, and commits the generated files when they change.

## Local Preview

Install Hugo extended v0.158.0 or newer, initialize submodules, and run:

```bash
git submodule update --init --recursive
hugo server
```

For a one-off production build:

```bash
hugo --gc --minify --cleanDestinationDir --destination public
```
