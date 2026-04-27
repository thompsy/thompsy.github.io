# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This is a personal Jekyll static site hosted at downthewire.co.uk, using the [Minimal Mistakes](https://github.com/mmistakes/minimal-mistakes) remote theme. It is deployed via GitHub Pages.

## Commands

```bash
# Install dependencies
bundle install

# Serve locally with live reload
bundle exec jekyll serve

# Build the site
bundle exec jekyll build
```

## Deploying changes

The site is hosted on GitHub Pages from the `master` branch of `git@github.com:thompsy/thompsy.github.io.git`. Pushing to `master` triggers an automatic rebuild and deploys to downthewire.co.uk (custom domain set via `CNAME`).

Workflow:
```bash
# Preview changes locally before pushing
bundle exec jekyll serve

# Commit and push to deploy
git add <files>
git commit -m "your message"
git push origin master
```

GitHub Pages builds the site after each push — changes typically go live within a minute or two.

## Architecture

The site uses `remote_theme: mmistakes/minimal-mistakes`, so theme files are not present locally — only overrides are committed.

Key files:
- `_config.yml` — all site-wide settings: author profile, footer links, navigation, plugins, and post defaults
- `_data/navigation.yml` — top navigation bar links
- `_layouts/home.html` — overrides the theme's home layout to add a custom welcome message
- `_pages/` — static pages (About, Thesis, archives, 404)
- `index.html` — entry point; uses the `home` layout

Content is sparse: the main pages are the home page and a thesis page (`/projects/jLTE-Simulator/`) linking to a downloadable PDF and related GitHub repos. There are no blog posts currently active (the posts section in the home layout is commented out).

Author sidebar links and footer links are configured separately in `_config.yml` under `author.links` and `footer.links`.
