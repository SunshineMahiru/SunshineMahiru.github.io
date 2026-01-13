# SunshineMahiru.github.io

A lightweight personal website, deployed as a static site on GitHub Pages.  
No frameworks, no build step, and no Jekyll processing (disabled via `.nojekyll`).

- Live (GitHub Pages): https://SunshineMahiru.github.io/
- Custom Domain (if configured): https://xizhou-sunshinemahiru.me/

## Features

- Simple, semantic, responsive HTML layout
- Light/Dark mode via `prefers-color-scheme`
- External stylesheet for better caching (`style.css`)
- Footer with placeholder ICP record (China mainland hosting compliance)
- PWA-ready manifest scaffold (`site.webmanifest`)
- Works fully as a static site — no Jekyll, no server

## Repository Structure

```
.
├─ index.html           # Homepage
├─ style.css            # Styles (external)
├─ .nojekyll            # Disable Jekyll on GitHub Pages (serve raw static files)
├─ CNAME                # Custom domain (optional, if using a custom domain)
├─ site.webmanifest     # PWA manifest scaffold (optional)
├─ favicon.ico          # Favicon (optional)
└─ assets/
   ├─ hero.jpg          # Example image (replace with your own)
   ├─ idea.jpg          # Example image (replace with your own)
   └─ icons/
      ├─ icon-192.png   # PWA icon (192x192)
      └─ icon-512.png   # PWA icon (512x512)
```

## Getting Started (Local)

No toolchain is required — just open `index.html` in your browser.

If you prefer a local server (for correct relative paths and caching):
```bash
# Python 3
python -m http.server 4000

# Node
npx serve .
```
Then open http://localhost:4000

## Deploying on GitHub Pages

This is a user site repository (`<username>.github.io`), so Pages deploys from the `main` branch root by default.

1. Ensure these files exist at the repository root:
   - `index.html`, `style.css`, `.nojekyll` (and optionally `CNAME`, `site.webmanifest`, `favicon.ico`)
2. In GitHub: Settings → Pages
   - Build and deployment → Source: “Deploy from a branch”
   - Branch: `main` and folder: `/ (root)`
3. Wait ~1–2 minutes for Pages to update.

### Using a Custom Domain

If you’re using a root domain like `xizhou-sunshinemahiru.me`, configure DNS:

- A records (recommended to add all 4):
  - `185.199.108.153`
  - `185.199.109.153`
  - `185.199.110.153`
  - `185.199.111.153`
- AAAA records (IPv6, optional but recommended):
  - `2606:50c0:8000::153`
  - `2606:50c0:8001::153`
  - `2606:50c0:8002::153`
  - `2606:50c0:8003::153`

For a `www` subdomain (optional), add:
- `CNAME` record: `www` → `SunshineMahiru.github.io`

Then in Settings → Pages:
- Set the Custom domain to your domain and Save
- Enable “Enforce HTTPS” (certificate issuance may take 10–60 minutes)

## Customization

- Text/content: edit `index.html`
- Styles/colors: edit CSS variables in `style.css` (`:root`)
- Images: replace `assets/hero.jpg` and `assets/idea.jpg` with your own
- Icons: place `assets/icons/icon-192.png` and `assets/icons/icon-512.png`
- Favicon: replace `favicon.ico`
- Manifest: tweak `site.webmanifest` (`name`, `short_name`, `theme_color`, `icons`, etc.)

Tip: Add a cache-busting query param when updating static files (e.g., `style.css?v=2`).

## Troubleshooting

- Cache: Force refresh (Ctrl/Cmd + F5) or add a query param: `/?v=timestamp`
- Check Pages status: Settings → Pages (look for errors or pending builds)
- Wrong branch/folder: Ensure `main` + `/ (root)` is selected
- 404 for assets: Verify the exact file paths (case sensitive)
- Custom domain DNS: Propagation can take 10–24 hours; verify A/AAAA records
- HTTPS not enabled: Wait for certificate issuance, then re-enable “Enforce HTTPS”
- Jekyll interference: Ensure `.nojekyll` exists in the repo root

## Contributing

PRs and suggestions are welcome for improvements to structure, accessibility, or performance.

---
Maintained by [SunshineMahiru](https://github.com/SunshineMahiru).
Contained AI help with this program.
