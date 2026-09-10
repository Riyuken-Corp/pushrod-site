# Pushrod Performance Cycle — deployable site

Static files. No build step, no server code.

- `index.html` — Full Revamp (single page, dark/light toggle, 42-photo gallery).
- `visual-refresh.html` — Visual Refresh (eight hash-routed pages, same copy as the current site).
- `support.js` — required runtime. Keep it next to the HTML files.
- `vendor/` — React 18.3.1 UMD builds served locally (the runtime is pointed at them via `window.__resources` in each page's head, so nothing loads from unpkg).
- `img/` — logo, gallery photos, shop photos, brand logos, payment icons.
- `_redirects` — old-URL redirects for Netlify / Cloudflare Pages.
- `about-us/`, `services/`, `engines/`, `products/`, `gallery/`, `testimonials/`, `contact-us/`, `home/` — redirect stubs for GitHub Pages.

## Deploy — GitHub Pages
1. Push the **contents of this folder** to `main` (files at the repo root, not nested).
2. Repo → Settings → Pages → Source "Deploy from a branch" → `main`, `/ (root)` → Save.
3. Live at `https://<user>.github.io/<repo>/` in a minute or two.

## Deploy — Netlify / Cloudflare Pages
Import the repo. Build command: none. Publish directory: `/`. `_redirects` is picked up automatically.

## External requests
Google Fonts (Barlow / Barlow Condensed) and the Google Maps embed on the contact
section. Both are keyless. Everything else is local.

## Notes
- Contact works without a server: `index.html` uses an "Email us" mailto button;
  `visual-refresh.html` uses a form that opens a pre-filled email. Neither posts anywhere.
- Theme follows the visitor's system setting and remembers a manual choice in localStorage.
- To publish the Visual Refresh instead, swap the two filenames.
