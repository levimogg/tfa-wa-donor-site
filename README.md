# TFA Washington donor site

Source for the donor-facing "Frontier Leadership" page. One HTML file with its styles inline, a small badge stylesheet, and the TFA logo set. No build step, no framework, no JavaScript beyond the scroll animations already in `index.html`.

Live at https://www.teachforamericawashington.com (GitHub Pages, served from the `main` branch of this repo). Every commit to `main` republishes the site, usually within a minute or two. Hard refresh if you still see the old version.

Project background, the donor-journey rationale, the verified alumni list with sources, and the archived v1 multi-page version all live in the private repo [levimogg/tfa-wa-donor-hub](https://github.com/levimogg/tfa-wa-donor-hub) (see `PROJECT.md` there).

## Files

- `index.html`: the whole page. Brand colors are variables at the top of the `<style>` block (`--blue`, `--navy`, `--red`, `--maroon`, `--cream`). Content starts at `<body>`.
- `mockup.css`: the "Mockup | Internal Review" badge in the corner. Remove the `<link rel="stylesheet" href="mockup.css">` line in `index.html` when the page is ready for donors.
- `logos/`: TFA logo SVGs, three families (35th anniversary cube, one-line wordmark, three-line stacked) in five brand colors. The page uses `tfa_logo_1L_cream_FFEED4.svg` in the header and as the favicon.
- `robots.txt` plus `<meta name="robots" content="noindex,nofollow">` in `index.html`: keep search engines out while the page is in review. Remove both when it goes public.
- `CNAME`: the custom domain for GitHub Pages. Do not delete it.
- `.nojekyll`: tells GitHub Pages to serve the files as-is.

Fonts (Libre Baskerville, Poppins) load from Google Fonts.

## What still needs work

Every photo is a placeholder: the hero box ("Corps member or student photo") and the 15 `<div class="photo">Photo</div>` cards in the leaders section. Investment tiers ($5K / $10K / $25K / $50K+) are unconfirmed. See `PROJECT.md` in the hub repo for the full list.

## Editing

Edit on GitHub (open the file, pencil icon, commit) or clone the repo and edit locally. To preview locally, open `index.html` in a browser.

## Hosting

- GitHub Pages: Settings > Pages, source `main` / root.
- Custom domain: `www.teachforamericawashington.com`, set in Settings > Pages and recorded in `CNAME`.
- DNS at the registrar:
  - `www` CNAME record pointing to `levimogg.github.io`
  - Apex (`@`) A records pointing to `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`, so the bare domain redirects to `www`
- Enforce HTTPS in Settings > Pages once GitHub finishes checking the domain (usually minutes, up to 24 hours).

The earlier review copy at https://tfa-wa-frontier-review.netlify.app is a manual Netlify deploy of the same `index.html`; it is not connected to this repo and will not update.
