# AGENTS.md

## Project type

Static HTML/CSS coursework portfolio. No build step, no package manager, no dependencies, no tests. Open `index.html` directly in a browser.

## Structure

- `index.html` — portfolio hub page (inline styles only, no external CSS link)
- `N-M.html` — individual practice pages, each self-contained with inline `<style>` blocks
- `css.css` — standalone stylesheet exercise; **not linked** from any HTML file
- `img/` — image assets referenced by some practice pages
- `new-4/` — empty directory

## Conventions

- All CSS class names, ID names, and JS variables must start with `zhang_` (e.g. `zhang_hero`, `zhang_work-card`, `zhang_box`).
- Some filenames contain Chinese characters; links in `index.html` use URL-encoded paths (e.g. `5-1%E5%B1%82%E5%8F%A0%E4%B8%8E%E7%BB%A7%E6%89%BF.html`). Preserve this encoding when editing links.
- Pages use native HTML/CSS only — no CDN, no frameworks, no external resources.
- `index.html` uses `lang="zh-CN"`; practice pages use `lang="en"`. Match the existing page when editing.

## What to check before finishing

- Verify all links in `index.html` resolve to actual filenames (watch for encoding mismatches).
- If adding a new practice page, add a corresponding card to the `work-list` grid in `index.html`.
