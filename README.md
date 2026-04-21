# Project Hub — Soar Beyond Team Hub (Static Site)

A lightweight, static internal “Team Hub” site built with plain **HTML + CSS**. The homepage (`index.html`) presents tiles grouped into **Tools**, **Guides**, and **Company Info**, each linking to a corresponding detail page.

## Quick start (local preview)

Because this is a static site, you can open `index.html` directly in a browser. For best results (correct relative paths and a more “production-like” preview), run a tiny local web server from the repo root:

```bash
python3 -m http.server 8000
```

Then visit `http://localhost:8000`.

## Editing content

### Update the hub (homepage tiles)

- Edit `index.html`
- For each tile, update:
  - Icon (emoji)
  - Title + description text
  - `href` (the page it should open)
- Update the “X items” count shown in each section header when adding/removing tiles.

### Update an inner page (tool / guide / company info)

- Edit the corresponding HTML file for that page
- Update the inner hero (badge, title, subtitle)
- Replace the placeholder content cards with real content

## Project structure

`style.css` is shared across all pages for consistent branding and layout.

The **intended** structure (as referenced by links in `index.html`) is:

```text
/
  index.html
  style.css
  tools/
    tool-one.html
    tool-two.html
    tool-three.html
  guides/
    guide-one.html
    guide-two.html
  company-info/
    company-info-one.html
```

### Note about current repo layout

At the moment, the HTML pages are in the repo root (for example `tool-one.html`, `guide-one.html`), while `index.html` links to `tools/...`, `guides/...`, and `company-info/...` paths. Also, the inner pages currently reference the stylesheet as `../style.css` (which assumes they live inside those subfolders).

To make navigation work end-to-end, either:

- **Option A (recommended)**: create `tools/`, `guides/`, and `company-info/` folders and move the corresponding pages into them, or
- **Option B**: keep everything at the repo root and update `index.html` links and each inner page’s stylesheet/link paths accordingly.

## Deployment

This project is designed for simple static hosting (e.g. Netlify). The existing page header comments indicate a workflow of **pushing to GitHub and letting Netlify deploy automatically**.

## Tech

- HTML (no build step)
- CSS (`style.css`)
- Google Fonts (DM Sans) as a web fallback for Aptos

