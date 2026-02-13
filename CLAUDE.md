# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Personal portfolio website (ripandy.github.io) deployed on GitHub Pages. This is a single-file static site with no build system, no package manager, and no bundler.

## Development

No build or install steps. Open `index.html` directly in a browser or serve with any static file server. Deployed automatically via GitHub Pages from the `main` branch.

## Architecture

The entire application lives in `index.html` (~614 lines) — HTML, CSS, and JavaScript are all inline. There is no component framework, no state management, and no module system.

### CDN Dependencies (loaded in HTML)

- **Tailwind CSS** — utility-first styling with custom theme (dark mode, custom colors, Inter + Fira Code fonts)
- **Chart.js** — radar chart for skills visualization
- **Font Awesome 6.4.0** — icons
- **Google Fonts** — Inter (300/400/600/700), Fira Code (400/500)

### Tailwind Configuration (inline)

Custom theme colors: `dark` (#0f172a), `darker` (#020617), `accent` (#3b82f6), `codeBg` (#1e293b), `textGray` (#94a3b8). Dark mode uses `class` strategy. Custom fonts defined as `sans` (Inter) and `mono` (Fira Code).

### Page Sections (anchor navigation)

`#about` | `#skills` | `#projects` | `#experience` | `#contact`

### Key Patterns

- Mobile-responsive with Tailwind breakpoints (`md:`) and a hamburger menu toggle via inline `onclick`
- Chart.js radar chart initialized on `DOMContentLoaded`
- Custom CSS classes: `.text-gradient` (gradient text), `.token.*` (syntax highlighting in code blocks)
- Custom webkit scrollbar styling
- Images stored in `images/` directory
