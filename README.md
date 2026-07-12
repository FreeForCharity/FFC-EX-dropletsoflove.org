# FFC-EX-dropletsoflove.org

Droplets of Love — FFC-supported charity website (static, GitHub Pages).

This repository holds a fully localized static capture of the former WordPress site at
`dropletsoflove.org`, migrated as part of the FFC Wave-1 WordPress-to-Pages program
([FFC-Cloudflare-Automation#702](https://github.com/FreeForCharity/FFC-Cloudflare-Automation/issues/702)).

## Hosting

- Deployed to GitHub Pages on the default URL:
  <https://freeforcharity.github.io/FFC-EX-dropletsoflove.org/>
- Deployment runs from `.github/workflows/static.yml` on every push to `main`.
- No custom domain and no DNS changes are configured at this stage.

## Migration notes

- Migrated from a WordPress site using the GiveWP donation plugin. The GiveWP donation-form and donor-dashboard embeds pointed at dynamic WordPress endpoints that do not survive a static migration; they were neutralized and need a static donation provider (e.g. Givebutter/Donorbox) — see the tracking issue. Two YouTube embeds are retained.
- All CSS/JS/fonts/images are served from this repository; Google Fonts and any external
  image hosts were downloaded and localized, and WordPress analytics/tracking beacons were stripped.
- `wp-json`, XML-RPC, oEmbed, RSS feed, and comment artifacts were stripped.
- Non-functional WordPress search/contact forms were neutralized; Cloudflare-obfuscated
  emails were decoded to `mailto:` links; dead internal links/images were pruned.

## CI

- `static.yml` — deploys to Pages on every push to `main`.
- `check-assets.yml` — fails if any asset loads from an external host.
- `linkcheck.yml` — lychee link check (weekly + on push/PR).

---

Supported by [Free For Charity](https://freeforcharity.org).
