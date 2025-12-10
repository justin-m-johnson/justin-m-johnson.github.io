# Copilot Instructions for justin-m-johnson.github.io

## Project Overview
- This repository is a Jekyll-powered personal site (static) for Justin Johnson.
- Content is authored under the `content/` collection and rendered using local `_layouts` and `_includes` (not a remote theme).

## Key Files & Directories
- `_config.yml`: site settings, plugins, `collections_dir: content`, pagination and defaults.
- `content/`: primary collection for posts/pages (front-matter controlled).
- `_layouts/` and `_includes/`: site templates — change layout here to affect pages.
- `_sass/`, `assets/`: styles and static assets (images, icons).
- `Gemfile`: Ruby gems used by Jekyll (install with `bundle install`).
- `CNAME`: custom domain for GitHub Pages.

## Local development & common commands
- Install dependencies: `bundle install` (uses the `Gemfile`).
- Serve locally (with livereload if desired):
  - `bundle exec jekyll serve --livereload`
- Build for production:
  - `JEKYLL_ENV=production bundle exec jekyll build`
- Exported site is generated into `./_site` (see `_config.yml` `destination`).

## Project-specific patterns and conventions
- The Jekyll `collections_dir` is set to `content`. New posts/pages belong under `content/`.
- Defaults in `_config.yml` set `layout: post`, `author: "Justin"`, and provide an `img` placeholder — include similar front-matter when creating posts.
- Images are typically referenced from `assets/`; the `img` collection is defined in `_config.yml` (see `collections.img`).
- Relative links are enabled via `jekyll-relative-links` plugin — prefer relative paths for internal links.

## Example: New post front-matter
```
---
title: "My Post Title"
date: 2025-12-07
layout: post
author: Justin
img: /assets/img/example.jpg
tags: [grc, cmmc]
---
```

## Build/CI notes
- GitHub Pages will serve the `main` branch using the repository settings or CI pipeline if configured; use the `CNAME` file to set the custom domain.
- Confirm plugins listed in `_config.yml` are supported on GitHub Pages; if not, build with GitHub Actions that run `bundle exec jekyll build` and then deploy the `_site` folder.

## What to ask the maintainer
- Clarify whether to use GitHub Pages native build or a custom GitHub Actions workflow for plugin compatibility.
- Preferred URL structure for new collections or special pages (if adding custom permalinks).

## Useful quick references (files to inspect)
- `_config.yml` — site-wide configuration (start here).
- `content/` — existing posts and sample front-matter.
- `_layouts/` and `_includes/` — how pages are constructed and which variables are available (e.g., `site`, `page`, `site.data`).
- `Gemfile` — which gems are required locally for development.

If any section here is unclear or you want more examples (e.g., how tags/taxonomies are implemented, or a sample GitHub Actions workflow), tell me which area to expand.
