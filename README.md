# Website-ZXBuilder

Public marketing + trial-request site for **ZXBuilder** — a bidirectional OpenUSD ↔ Autodesk Revit plugin for semiconductor fabs and industrial digital twins.

## Live

- Site: <https://www.zxbuilder.club>
- Hosting: GitHub Pages (CNAME → `www.zxbuilder.club`)
- Apex `zxbuilder.club` redirects to `www`.

## Relationship to zigma.club

`zigma.club` and `zxbuilder.club` run **in parallel** (both live, no redirect between them).
Release assets are served from a single source — the `Website-ZigmaClub` releases — so the
download / update-check chain used by existing installations stays unchanged.

## Structure

- `index.html` — single-page site, 4 languages (EN / 繁中 / 日本語 / 한국어), inline i18n
- `CNAME` — custom domain for GitHub Pages
- `robots.txt`, `sitemap.xml` — crawler directives
- `version.json` — version + download endpoints consumed by the in-product update check
- `img/` — screenshots
- `public/downloads/` — legacy toolkit archives
- `.github/workflows/pages.yml` — Pages deployment

## Notes

- Product UI inside Revit still shows the **Zigma** tab; on-page wayfinding text keeps that
  wording deliberately so users can find it. It changes when the plugin UI is renamed.
- Release filenames (`ZigmaSetup_*.msi`) are intentionally unchanged during Pre-Beta.
