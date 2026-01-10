# WARP.md

This file provides guidance to WARP (warp.dev) when working with code in this repository.

## Project Overview
Octo Ventures is a static HTML/CSS portfolio site hosted on GitHub Pages. The site includes multiple pages (index, about, services, testimonials, contact) with responsive design and integrated chat functionality via Genesys.

## Architecture
The project uses a simple static site structure:
- **Root HTML files** (`index.html`, `about.html`, `services.html`, `testimonials.html`, `contact.html`) - main page templates using a common navigation header and footer
- **CSS** (`css/style.css`) - centralized style sheets for all pages; uses responsive design patterns
- **Media assets** (`media/images/`) - logo and other images referenced across pages
- **GitHub Pages deployment** - configured via CNAME file to serve at `zacharhill.co`
- **CI/CD** (`.github/workflows/test.yml`) - runs super-linter on push and pull requests to main/master branches

## Common Commands
- **Lint the codebase**: The super-linter GitHub Action runs automatically on push/PR to main. To validate locally before committing, reference the super-linter configuration in `.github/workflows/test.yml`
- **View the site locally**: Open any HTML file directly in a browser, or use a simple HTTP server: `python3 -m http.server 8000` then navigate to `http://localhost:8000`
- **Deploy**: Push to `main` branch - GitHub Pages automatically deploys from this branch

## Important Notes
- All HTML pages share common navigation and footer patterns - keep these consistent across files
- The site is deployed via GitHub Pages
- CSS is centralized in a single stylesheet; be careful with selector specificity to avoid unintended cascade effects
