# AGENTS.md

This file provides guidance to AI coding agents (Warp, Claude Code, Cursor, Codex, and others) when working with code in this repository.

## Project Overview
Octo Ventures is a static HTML/CSS portfolio site hosted on GitHub Pages. The site includes multiple top-level pages (index, about, services, testimonials, contact) plus a set of detailed service pages, all with responsive design.

## Architecture
The project uses a simple static site structure:
- **Root HTML files** (`index.html`, `about.html`, `services.html`, `testimonials.html`, `contact.html`) - main page templates using a common navigation header and footer
- **Service detail pages** (`services/cio-cto.html`, `services/ai-data-ml.html`, `services/cloud.html`, `services/devsecops.html`) - in-depth pages for each service offering, linked from `services.html`
- **CSS** (`css/style.css`) - centralized style sheet for all pages; uses responsive design patterns
- **Media assets** (`media/images/`) - logo and other images referenced across pages
- **GitHub Pages deployment** - configured via CNAME file to serve at `zacharhill.co`
- **CI/CD** (`.github/workflows/test.yml`) - runs super-linter on push and pull requests to main/master branches

## Common Commands
- **Lint the codebase**: The super-linter GitHub Action runs automatically on push/PR to main. To validate locally before committing, reference the super-linter configuration in `.github/workflows/test.yml`
- **View the site locally**: Open any HTML file directly in a browser, or use a simple HTTP server: `python3 -m http.server 8000` then navigate to `http://localhost:8000`
- **Deploy**: Push to `main` branch - GitHub Pages automatically deploys from this branch

## Important Notes
- All HTML pages share common navigation and footer patterns - keep these consistent across files, including the ones under `services/`
- The site is deployed via GitHub Pages
- CSS is centralized in a single style sheet; be careful with selector specificity to avoid unintended cascade effects
- Always create a feature branch for changes and open a pull request rather than committing directly to `main`
