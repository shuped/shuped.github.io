# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Personal blog built with Jekyll 4.3, deployed to GitHub Pages via GitHub Actions. The site focuses on AI development, software engineering, and technical learnings.

## Development Commands

```bash
# Install dependencies
bundle install

# Run local development server (http://localhost:4000)
bundle exec jekyll serve

# Build for production
bundle exec jekyll build
```

## Architecture

**Jekyll Structure:**
- `_posts/` - Blog posts in markdown (format: `YYYY-MM-DD-title.md`)
- `_layouts/` - Page templates (default.html → home.html/post.html)
- `_includes/` - Reusable HTML partials (head, header, footer)
- `_sass/` - SCSS partials imported by `assets/css/main.scss`
- `_config.yml` - Site configuration and metadata

**Post Front Matter:**
```yaml
---
layout: post
title: "Post Title"
date: YYYY-MM-DD
categories: [AI]  # Options: ai, development, learnings
---
```

**Deployment:**
- Pushes to `main` branch trigger the GitHub Actions workflow (`.github/workflows/deploy.yml`)
- Current working branch is `master`
