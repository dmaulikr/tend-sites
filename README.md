# Tend — public website

Static one-pager + privacy + support pages for the Tend iOS app. Three plain HTML files, one CSS file. Zero build step. Free to host anywhere.

## Files

| File | Purpose |
|---|---|
| `index.html` | Landing page — brand mark, tagline, feature grid, mailto |
| `privacy.html` | **Privacy policy** — the URL you paste into App Store Connect |
| `support.html` | **Support page** with FAQ — also App Store Connect–required |
| `404.html` | Soft fallback in Tend's voice |
| `style.css` | All visual styles (light + dark mode auto-switching) |
| `CNAME` | Custom domain — currently set to `tend.aithelianlabs.com`. Edit or delete to use the default `*.github.io` URL. |

## Deploy on GitHub Pages (5 minutes, free)

### Option A — dedicated repo

1. Create a new public repo: `tend-web` (or any name).
2. Copy these files to the repo root:
   ```
   index.html
   privacy.html
   support.html
   404.html
   style.css
   CNAME            # only if using a custom domain
   ```
3. Push to GitHub.
4. Repo → **Settings** → **Pages** → Source: `Deploy from a branch`, Branch: `main`, Folder: `/ (root)`. Save.
5. Wait ~30 seconds. Your URLs:
   - `https://YOUR_USERNAME.github.io/tend-web/`
   - `https://YOUR_USERNAME.github.io/tend-web/privacy.html`
   - `https://YOUR_USERNAME.github.io/tend-web/support.html`

### Option B — user/organization site

If you want `https://YOUR_USERNAME.github.io/` directly (no `/tend-web/` subpath), name the repo `YOUR_USERNAME.github.io`.

### Option C — custom domain (recommended for tend.aithelianlabs.com)

1. Edit `CNAME` to your subdomain (e.g. `tend.aithelianlabs.com`). Already set.
2. At your DNS provider (Cloudflare, Route 53, etc.), add a `CNAME` record:
   ```
   tend.aithelianlabs.com → YOUR_USERNAME.github.io
   ```
3. Repo → Settings → Pages → Custom domain → enter your subdomain → Save.
4. Wait ~5 min for HTTPS to provision. Your URLs:
   - `https://tend.aithelianlabs.com/`
   - `https://tend.aithelianlabs.com/privacy.html`
   - `https://tend.aithelianlabs.com/support.html`

## What to paste into App Store Connect

| Field | URL |
|---|---|
| **Privacy Policy URL** *(required)* | `https://YOUR_DOMAIN/privacy.html` |
| **Support URL** *(required)* | `https://YOUR_DOMAIN/support.html` |
| **Marketing URL** *(optional)* | `https://YOUR_DOMAIN/` |

## Checking your work

Open each page in your phone's browser and:

- [ ] Pages render in both light and dark mode (toggle iPhone Settings → Display & Brightness)
- [ ] Text is readable, links are visible, brand mark renders correctly
- [ ] `mailto:` links open Mail
- [ ] Footer links work
- [ ] 404 — visit a fake URL like `/whatever.html` → soft fallback

## Optional polish

- Add a real Open Graph image (1200×630) for prettier link previews — drop a `og.png` in the repo root and update the `og:image` meta tag in `index.html`.
- Add Plausible / Fathom for privacy-friendly analytics — *or don't*, in keeping with Tend's no-tracking promise.

## License

Source for these pages is intended for hosting Tend's own public site. The Tend brand mark, copy, and visual identity are proprietary.
