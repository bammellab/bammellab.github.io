# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is the GitHub Pages documentation site for Bammellab, focused on molecular visualization on Android. It uses **Hugo** with the **Hugo-Octopress** theme to generate a static site deployed to the `gh-pages` branch.

## Build and Deploy

- **Build docs locally**: `hugo server` (runs dev server at localhost:1313)
- **Build for production**: `hugo` (outputs to `public/`)
- **Build optimized**: `hugo --gc --minify` (garbage collect and minify)
- **Deploy**: Automatic via GitHub Actions on push to `master` (see `.github/workflows/hugo.yml`)
- **Gradle** (6.5.1) is present for Kotlin/PDB parser subprojects but is not used for the docs site itself

## Git / Push

- Remote: `https://bammellab@github.com/bammellab/bammellab.github.io.git`
- Push with user `bammellab`: `git push origin master`

## Architecture

- `hugo.toml` — Site configuration, navigation menu, theme settings
- `content/` — All markdown content pages with Hugo front matter (flat structure, no subdirectories)
- `layouts/` — Custom layout overrides (e.g., `index.html` for home page)
- `static/img/` — Image assets
- `themes/Hugo-Octopress/` — Theme (git submodule)
- `build.gradle` / `settings.gradle` — Gradle config for Kotlin subprojects (group: `com.kotmol.kotmolpdbparser`)

## Content Structure

Pages document PdbViewer Android app demos, PDB molecular structure notes, special/unusual PDB files, and the GamepadTest Android app. Video pages contain extensive lists of PDB entry IDs with links to RCSB.

## Key Details

- Theme: Hugo-Octopress (requires Hugo >= 0.146.1)
- Site URL: https://bammellab.github.io/
- Goldmark renderer has `unsafe = true` — raw HTML in markdown content is rendered as-is
- Content changes go in `content/*.md`; navigation changes go in `hugo.toml` under `[menu]`
