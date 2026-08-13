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

| Site | Owner | Publish path |
|---|---|---|
| `zigma.club` | plugin mesh | `tools\ship-zigmaclub.ps1` (automated) |
| `zxbuilder.club` | **RM Office** | **manual commit + push to this repo** — no automation exists |

⚠️ Because this site has **no publish script**, a new release does **not** reach it automatically.
Version and download links here must be updated by hand after the release is live.

## Structure

- `index.html` — single-page site, 4 languages (EN / 繁中 / 日本語 / 한국어), inline i18n
- `CNAME` — custom domain for GitHub Pages
- `robots.txt`, `sitemap.xml` — crawler directives
- `version.json` — version + download endpoints consumed by the in-product update check
- `img/` — screenshots
- `public/downloads/` — legacy archives (v5.5.x); not linked from the current page
- `.github/workflows/pages.yml` — Pages deployment

## Code signing

From **v5.7.8.5** onward the released MSI is digitally signed with an **EV code-signing
certificate** issued to *Reality Matrix AI Inc.* Windows shows Reality Matrix AI Inc. as the
verified publisher.

Consequences for this site — already applied:

- The "MSI is not yet code-signed / SmartScreen Unknown Publisher" banner is **removed** in all four
  languages and replaced with the signed-publisher notice.
- The **Diagnostic Toolkit** download is **removed** — it existed to troubleshoot install failures
  caused by the unsigned installer.
- The **ZIP alternative is kept**, but re-framed: it is for users whose *corporate IT policy* blocks
  `.msi` downloads, not for working around Microsoft/SmartScreen.

⚠️ The `README.txt` install guide shipped as a **release asset** is produced by the plugin build, not
by this repository. It still contains SmartScreen instructions and must be regenerated on the plugin
side for v5.7.8.5.

## Notes

- Product UI inside Revit still shows the **Zigma** tab; on-page wayfinding text keeps that
  wording deliberately so users can find it. It changes when the plugin UI is renamed.
- Release filenames (`ZigmaSetup_*.msi`) are intentionally unchanged during Pre-Beta.
