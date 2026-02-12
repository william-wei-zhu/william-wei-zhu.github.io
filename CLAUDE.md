# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Static personal portfolio website hosted on GitHub Pages at **williamzhu.ai** (custom domain via Cloudflare DNS, configured in `CNAME`). Built with vanilla HTML, CSS, and Bootstrap 4.5.0 (via CDN). No build system, no Node.js, no JavaScript frameworks.

## Development

There is no build step. To preview locally, serve the root directory with any static HTTP server:

```
python -m http.server
```

Deployment is automatic via GitHub Pages on push to the default branch.

## Architecture

- **`index.html`** — Landing/About Me page (site root)
- **`webpages/`** — All subpages and their CSS files. Each page has a matching CSS file (e.g., `projects.html` + `projects.css`)
- **`img/`** — Images and icons (~393MB). Subdirectories: `books/`, `projects/`
- **`pdf/`** — Resume and academic papers

Pages: About Me (`index.html`), Projects, Papers, Resume (embedded PDF), Favorite Books, and detailed project pages (demystify, divvy, the_office).

## Conventions

- **Shared header/navbar** is copy-pasted across all pages (not templated). Changes to the header or nav must be replicated in every HTML file.
- **CSS per page** — each page has its own CSS file in `webpages/`. The landing page uses `webpages/frontpage.css`.
- **Card layout pattern** — projects, papers, and books use a consistent structure: `div.book > img + div.bookinfo > (p.title + div.author + p.comment)`.
- **Bootstrap 4.5.0** for grid (`container`, `row`, `col-lg-*`) and navbar. jQuery 3.5.1 slim for navbar toggle only.
- **Responsive breakpoint** at 768px via `@media` queries in each CSS file.
- **Font:** Optima. **Background:** #FAFFFA.
- **Active nav item** — each page sets `.nav-item.active` on its own link.
- Paths between pages use relative URLs (e.g., `../img/`, `../webpages/`).
