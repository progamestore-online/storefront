# ProGameStore brand

The brand guide is [`brand/BRAND.md` in `progamestore-online/platform`](https://github.com/progamestore-online/platform/blob/main/brand/BRAND.md). Identity, asset list, usage rules and the update procedure live there.

## In this repo

- **Deployment is gated:** this catalogue is dormant. Pushes validate and build only; `progamestore-online/marketing` owns the live site at progamestore.online. Replacing it takes a manual workflow dispatch with `launch_catalogue=true`, which is outside branding maintenance.
- **Served files** at the repo root, copied to `dist/` by `build.js`: `favicon.svg`, `apple-touch-icon.png`, `icon-192.png`, `icon-512.png`, `og-image.png`.
- **Full export:** `brand/assets/` holds the 17-file kit export.
- **Fonts:** Manrope and Fraunces are self-hosted in `fonts/`, with their licence files, and copied to `dist/fonts/`.
- **Cache parameter:** asset and manifest icon URLs in the pages, templates and `manifest.json` carry `?v=2026-11-18`, the kit version. Bump it when replacing kit assets so returning browsers fetch the new files.
- **Themes:** keep the automatic light/dark behaviour and the explicit theme choice.
