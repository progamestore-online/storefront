# progamestore-online/storefront

The catalog at https://progamestore.online — a curated marketplace for paid multiplayer browser games.

## What it is

Static site, no backend. `build.js` reads `registry.json` and templates the listing + per-game detail pages, then `dist/` deploys to Cloudflare Pages.

Vendored from `freegamestore-online/freegamestore` on 2026-05-20 and rebranded for the Pro tier (violet accent, subscription pricing, multiplayer-first copy).

## Develop

```bash
node build.js
cd dist && python3 -m http.server 9876
# open http://localhost:9876
```

## Add a game

Edit `registry.json`. Each game declares:
- `id`, `name`, `category`, `icon`, `iconBg`, `description`
- `appUrl` (e.g. `https://chess.progamestore.online`)
- `repo` (e.g. `progamestore-online/chess`)
- `price`: `{ model, amountUsd, period, trialDays }`
- `features`: list of bullet points for the detail page

Push to main; CF Pages auto-deploys.

## Layout

- `templates/index.html` + `templates/game-detail.html` — string-replaced by `build.js`
- `*.html` at root — static pages (about, pricing, guidelines, etc.)
- `style.css`, `theme.js`, `search.js`, `storefront.js` — copied to `dist/` as-is
- `registry.json` — source of truth for the catalog

## Differences from `freegamestore-online/freegamestore`

- Violet accent (`#9333ea`) instead of emerald
- "Premium web games" copy, subscription pricing model
- No quality dashboard yet (PGS doesn't have a scheduled auditor)
- No leaderboard pages (per-game leaderboards live in the games themselves)
- No "Get Started" / "Build" pages (those live in the platform docs)
- Cross-store search points at FreeGameStore (free-game alternatives) instead of FreeAppStore
