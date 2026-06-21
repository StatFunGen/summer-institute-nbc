---
title: "About This Site"
weight: 2
---

# About This Site

This repository is configured as a Hugo site using the Hugo Book theme.

When Markdown content is pushed to `main`, GitHub Actions builds the static site
and commits the generated HTML files under `public/` back to this repository.
This workflow generates files only; it does not deploy through GitHub Pages.

## Writing Content

Create or edit Markdown files under `content/docs/`. Use standard Hugo
frontmatter at the top of each file:

```yaml
---
title: "Lecture Title"
weight: 10
---
```

Lower `weight` values appear earlier in the sidebar.
