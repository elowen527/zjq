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

- All CSS class names, ID names, and JS variables must start with `zjq_` (e.g. `zjq_hero`, `zjq_work-card`, `zjq_box`). Existing `zhang_` names in older pages stay as-is unless the user explicitly asks for a refactor.
- Every newly created HTML file must include a header comment with author, creation time, the LLM model used, and feature name: `<!-- 姓名：张钧乔，建立时间：YYYY-MM-DD HH:mm:ss，使用的大模型：模型名，功能名称：页面功能描述 -->`. When editing an older page that lacks it, add the comment (for legacy pages the model field can be omitted or filled with the model that last edited it).
- Some filenames contain Chinese characters; links in `index.html` use URL-encoded paths (e.g. `5-1%E5%B1%82%E5%8F%A0%E4%B8%8E%E7%BB%A7%E6%89%BF.html`). Preserve this encoding when editing links.
- Pages use native HTML/CSS/JS only — no CDN, no frameworks, no third-party libraries, no external resources.
- Icons must come from the local `font/` directory (Alibaba iconfont: `font/iconfont.css` + `iconfont-*.woff2`), referenced via `<link>` to the local stylesheet and `<span class="iconfont icon-xxx">` classes. Do not use Font Awesome, Lucide, or any other icon library. Legacy pages using `cdn/` stay as-is unless the user explicitly asks for a refactor.
- `index.html` uses `lang="zh-CN"`; practice pages use `lang="en"`. Match the existing page when editing.

## What to check before finishing

- Verify all links in `index.html` resolve to actual filenames (watch for encoding mismatches).
- If adding a new practice page, add a corresponding card to the `work-list` grid in `index.html`.
- New code uses the `zjq_` prefix and every new/edited HTML page contains the 姓名/日期/功能名称 header comment.
