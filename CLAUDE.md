# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

A static, single-page personal website/portfolio template. Plain HTML/CSS with no build system, package manager, or JavaScript framework — the entire site is two files.

- `Index.html` — the full page markup (about, blog list, projects, resume, contact sections), all currently filled with placeholder text ("Your Name", "Post Title 1", "Job Title | Company Name", etc.)
- `style.css` — all styling, driven by CSS custom properties defined in `:root` (`--primary-color`, `--accent-color`, `--bg-color`, `--spacing`, etc.)

## Development

There is no build, lint, or test tooling — open `Index.html` directly in a browser to preview changes, or serve the directory with any static file server. Edits are made directly to the two files.

## Architecture notes

- Layout uses a sticky-footer flexbox pattern on `body` (`display: flex; flex-direction: column; min-height: 100vh`) with `footer { margin-top: auto }`.
- Section-specific styles in `style.css` are grouped by the matching `id`/class from `Index.html` (`#about`, `.blog-post-summary`, `.project-grid`/`.project-card`, `#resume`, `.social-links`, etc.) — when adding a section to the HTML, add a matching block to the CSS rather than inline styles.
- Theming (colors, line-height, base spacing) is centralized in the `:root` custom properties at the top of `style.css`; prefer changing those over hardcoding new values.
- Responsive breakpoints are at 768px and 480px (`@media` queries at the bottom of `style.css`) — the nav stacks vertically and the project grid collapses to one column below 768px.
- Font Awesome is loaded via CDN (`cdnjs.cloudflare.com`) for icons; there is no local/bundled copy.
- The footer year is set at runtime by an inline `<script>` in `Index.html` (`document.getElementById('current-year')`) — this is the only JavaScript in the project.
- All content is placeholder — filling in real content (name, bio, posts, projects, resume, contact info/links) is the main expected task in this repo, not adding tooling.
