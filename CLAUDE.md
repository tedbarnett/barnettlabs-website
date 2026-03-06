# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Static portfolio website for Barnett Labs (Ted Barnett). No build tools, frameworks, or package manager — pure HTML + CSS served as static files.

## Architecture

- `index.html` — Portfolio page with a grid of project cards
- `about.html` — About/bio page
- `css/style.css` — Single stylesheet (CSS custom properties in `:root`, responsive breakpoints at 768px and 480px)
- `images/` — Project and portrait images
- `_headers` — HTTP header rules (likely for Cloudflare Pages or similar static hosting)

## Development

No build step. Open HTML files directly in a browser or use any local static server:

```
python -m http.server 8000
```

## Conventions

- Font: Inter (loaded from Google Fonts)
- Design tokens are CSS custom properties on `:root` (e.g. `--color-bg`, `--max-width`)
- Navigation uses `class="active"` on the current page link — must be set manually per page
- Images use `loading="lazy"` and `aspect-ratio: 4 / 3` with `object-fit: cover`
- Both pages share the same header/nav and footer markup (no templating — changes must be duplicated)
