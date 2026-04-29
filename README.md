# Music in the City · Companion App

NFC-triggered single-file PWA companion for **Music in the City Southampton** festival.

Visitors tap a RouteLoop NFC tag at any of 54 festival venues and are launched into a contextual mobile experience: what's playing now, what's on next, the full schedule for both days, an interactive map, the artist showcase, and a donation flow.

**Live:** https://music-in-the-city-soton-production.up.railway.app/

## Stack

- **Single-file HTML PWA** — all UI, data, logic in one `index.html`
- **Leaflet.js** for the venue map (lazy-loaded with multi-CDN fallback)
- **Web Share API** for native iOS/Android share sheet (custom fallback for desktop)
- **Caddy file-server** on **Railway** for hosting (static, zero-server)

## Partners

- **Music in the City CIC** — festival organiser, primary donation beneficiary
  ([musicinthecity.org](https://musicinthecity.org))
- **Saints Foundation** — RouteLoop NFC infrastructure, festival sponsor, secondary donation beneficiary
  ([saintsfoundation.co.uk](https://www.southamptonfc.com/en/saints-foundation-home))
- **Superspree Ltd** — app builder

## Deployment

Railway watches the `main` branch. Push to deploy:

```bash
git add index.html
git commit -m "Update to vX"
git push
```

Build + deploy takes ~60 seconds. The same URL serves the new version.

## Files

- `index.html` — the entire app (~300KB, all logic + data + embedded logos)
- `manifest.json` — PWA manifest for "Add to Home Screen"
- `icon-*.png` — PWA icons (192, 512, 180 Apple, maskable)
- `favicon.png` — browser tab icon
- `railway.json` + `nixpacks.toml` — Railway / Caddy deploy config

## Versions (kept locally, not in repo)

- v1: Original WMFF-pattern build
- v3: MITC red/white/yellow brand alignment
- v4: Touch-only scroll, Spotify integration
- v5: Sunday programme added (138 events total)
- v6: Web Share API integration
- v6-saints: Saints Foundation partnership
- v6-saints-pwa: PWA installable (current `index.html`)
