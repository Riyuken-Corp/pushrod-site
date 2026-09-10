# Pushrod Performance Cycle — website

Two self-contained pages. No build step, no dependencies, no server code.

- `index.html` — the **Full Revamp** (single page with recommendations, off-season section, FAQ, email/call buttons).
- `visual-refresh.html` — the **Visual Refresh** (same 8 pages/copy as the current site, restyled). Kept for comparison; delete it or rename it to `index.html` if you prefer this version.

Only external request is Google Fonts (Barlow / Barlow Condensed). The logo is embedded in the file.

## Try it locally
Open `index.html` in a browser. That's it.

## Deploy — GitHub Pages (public repo, free)
1. Create a new repository, e.g. `pushrod-site`, and push these files to the `main` branch.
2. Repo → Settings → Pages → Source: "Deploy from a branch" → Branch `main`, folder `/ (root)` → Save.
3. Site appears at `https://<user>.github.io/pushrod-site/` in a minute or two.

## Deploy — Netlify (private repo OK, free, working contact form)
1. netlify.com → Add new site → Import from Git → pick the repo. Build command: none. Publish directory: `/`.
2. Nothing else to configure — the contact section is an "Email us" button (mailto) plus click-to-call, so it works on any static host with no form service.

## Redirects from the old site's URLs
Google already knows the current eight URLs (`/services`, `/engines`, …). Two mechanisms are included so none of them 404:
- `_redirects` — read automatically by **Netlify** and **Cloudflare Pages**; sends each old path to the matching section of the new page with a permanent (301) redirect.
- `about-us/index.html`, `services/index.html`, etc. — stub pages for **GitHub Pages** (which has no server-side redirects); they forward instantly and are marked `noindex`. Harmless on Netlify/Cloudflare, where `_redirects` takes precedence.

## Custom domain
Point `pushrodperformancecycle.ca` at the host once you've confirmed the shop (not Yellow Pages) controls the registration:
- GitHub Pages: Settings → Pages → Custom domain, then add the A/CNAME records GitHub shows. HTTPS is automatic.
- Netlify: Site → Domain management → Add domain, then follow the DNS records shown.

## Before going live
- Photos live in `img/` — `img/gallery/01.avif`–`42.avif` are the customer photos (8 shown, the rest behind "Show all"), `img/shop/` holds the shop, owner, MVIS, S&S, engine and BBB images. Add a `<figcaption>` to any gallery photo once the shop supplies bike/work details.
- Confirm Saturday hours wording and the insurance-claims line with the shop.
- Swap the embedded logo for the original high-res file if the shop has one (`.brand .logo` and `.hero-logo` `src` attributes).
