# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

A static personal portfolio website — no build tools, no package manager, no framework. Pure HTML5, CSS3, and vanilla JavaScript.

## Development

No build or install steps required. Open `index.html` directly in a browser, or serve locally:

```bash
python3 -m http.server 8080
# or
npx serve .
```

## Architecture

Three files make up the entire site:

- **`index.html`** — Single-page layout with sections: hero, about, skills, projects, contact, CV download, footer. The `<head>` contains an inline theme script that runs before CSS loads to prevent flash-of-wrong-theme.
- **`style.css`** — Theme system via CSS custom properties on `:root` and `[data-theme="dark"]`. Container max-width is 900px. Responsive breakpoints at 900px (tablet) and 640px (mobile).
- **`main.js`** — Three concerns: theme toggle (persisted to localStorage), mobile nav hamburger, and scroll-reveal animations via IntersectionObserver.

## Theme System

Themes are driven by CSS variables. Dark mode activates via `data-theme="dark"` on `<html>`. The no-flash inline script in `<head>` checks `localStorage` and `prefers-color-scheme` before the page renders.

## Assets

`assets/cv.pdf` is the downloadable CV linked from both the hero section and the CV download band.
