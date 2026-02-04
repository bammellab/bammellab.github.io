# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is the GitHub Pages documentation site for Bammellab, focused on molecular visualization on Android. It uses **Hugo** with a custom minimal theme to generate a static site deployed via GitHub Actions.

## Build and Deploy

- **Development server**: `hugo server` (runs dev server at localhost:1313)
- **Build for production**: `hugo --gc --minify` (outputs to `public/`)
- **Deploy**: Automatic via GitHub Actions on push to `master` (see `.github/workflows/hugo.yml`)
- **Gradle** (6.5.1) is present for Kotlin/PDB parser subprojects but is not used for the docs site itself

## Git / Push

- Remote: `https://bammellab@github.com/bammellab/bammellab.github.io.git`
- Push with user `bammellab`: `git push origin master`

## Architecture

- `config/_default/hugo.toml` — Site configuration
- `config/_default/params.toml` — Theme parameters
- `config/_default/menus/menus.en.toml` — Navigation menu configuration
- `layouts/` — Custom theme layouts (baseof, single, list, index, partials)
- `static/css/style.css` — Theme styles with light/dark mode support
- `content/` — Homepage (`_index.md`)
- `content/docs/` — All markdown content pages with Hugo front matter
- `static/img/` — Image assets
- `package.json` — npm scripts for convenience (`npm run dev`, `npm run build`)
- `build.gradle` / `settings.gradle` — Gradle config for Kotlin subprojects (group: `com.kotmol.kotmolpdbparser`)

## Content Structure

Pages document MotmBrowser Android app, SimpleMusicPlayer, PDB molecular structure notes, special/unusual PDB files, and the GamepadTest Android app. Video pages contain extensive lists of PDB entry IDs with links to RCSB.

## Key Details

- Theme: Custom minimal theme with dark mode support
- Site URL: https://bammellab.github.io/
- Goldmark renderer has `unsafe = true` — raw HTML in markdown content is rendered as-is
- Content changes go in `content/docs/*.md`
- Navigation changes go in `config/_default/menus/menus.en.toml`
- Old URLs preserved via Hugo aliases (e.g., `/motm-browser/` redirects to `/docs/motm-browser/`)
