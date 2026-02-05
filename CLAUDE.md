# Interloom Website

Marketing and documentation website for Interloom, a custom automation platform.

## Tech Stack

- **Static Site Generator**: Eleventy (11ty) v2
- **Templating**: Nunjucks (.njk)
- **Styling**: Tailwind CSS v4 with `@theme` semantic tokens (Geist font)
- **Design System**: Shared `@theme` tokens from prototype-control-tower (`surface-1..4`, `fg-1..4`, `line`, tints). Serif headings use Hedvig Letters Serif.

## Commands

- `npm start` - Run dev server (Eleventy + Tailwind watch in parallel) at http://localhost:8080
- `npm run build` - Build for production (Tailwind minify + Eleventy with pathPrefix)

## Project Structure

```
src/
├── _data/          # Global data files
├── _includes/      # Layout templates (base.njk, docs.njk)
├── blog/           # Blog posts (markdown)
├── css/            # Tailwind entry (main.css with @theme tokens + @layer components)
├── docs/           # Documentation pages
├── images/         # Static images
├── pitches/        # Pitch/use-case pages
├── releases/       # Release notes
└── index.md        # Homepage
```

## Content Collections

Defined in `.eleventy.js`:
- **posts** - Blog posts from `src/blog/*.md`
- **releases** - Release notes from `src/releases/*.md`
- **pitches** - Pitch pages from `src/pitches/*.md`
- **docs** - Documentation from `src/docs/*.md` (sorted by `order` frontmatter)

## Adding Content

Create markdown files with frontmatter:

```md
---
title: Page Title
layout: base.njk
date: 2025-01-15
---

Content here...
```

For docs, add `order: N` to control sidebar order.

## Deployment

GitHub Pages with `pathPrefix: /interloom-marketing-website/` in production (set via `ELEVENTY_ENV=production`).
