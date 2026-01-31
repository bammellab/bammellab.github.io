Bammellab
==========

https://bammellab.github.io/

Visualization on the Android Platform — exploring visualization design and tools aimed at Molecular Biology.

## Site

This is a [Hugo](https://gohugo.io/) static site using the [Hugo-Octopress](https://github.com/parsiya/Hugo-Octopress) theme, deployed to GitHub Pages via GitHub Actions.

## Build locally

```bash
hugo server
```

## Deploy

Pushes to `master` automatically build and deploy via the GitHub Actions workflow in `.github/workflows/hugo.yml`.

## Structure

- `hugo.toml` — Site configuration and navigation menu
- `content/` — Markdown content pages
- `layouts/` — Custom layout overrides
- `static/img/` — Image assets
- `themes/Hugo-Octopress/` — Theme (git submodule)
