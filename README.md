# ✈️ TripTrack — Expedition Budget Tracker

A lightweight, offline-first Progressive Web App (PWA) for tracking expenses during trips, treks, and expeditions. Built by a uni student on a Spiti Valley trek who got tired of losing track of where the money was going.

---

## The Origin

TripTrack started as a simple problem during a trek—I couldn’t easily keep track of my expenses or know how much I had left. Existing tools either required internet, felt too complex, or didn’t give a clear view of spending for a single trip.

TripTrack is a lightweight, offline-friendly solution that helps track expenses quickly and gives a clear overview of spending throughout a trip.

---

## Features

### Core
- **Trip setup** — name your expedition, set a total budget, pick a currency, and define how many days the trip runs
- **Budget lock** — once you lock your budget, it's protected from accidental edits; adjust it intentionally with the increase/decrease controls
- **Offline-first** — works fully without internet via a service worker; your data never leaves your device

### Expense Tracking
- **Per-day logging** — tag each expense to a specific day so you can see how spending varied across the journey
- **8 categories** — Food & Drink, Travel & Transport, Stay & Lodging, Activities & Entry, Shopping, Medical & Safety, Fuel, Other
- **Optional notes** — add context to any expense (e.g., "overpriced chai at the pass")
- **Delete with confirmation** — remove mistakes without accidentally wiping things

### Insights
- **Spending bar** — header-level progress bar showing how much of the budget is used; shifts green → amber → red as you approach the limit
- **Category breakdown** — visual bar chart of spending per category so you instantly see where the money went
- **Daily average** — calculates your spend-per-day based on logged days so you know if you're on pace
- **Top category** — at-a-glance stat showing your biggest spending area
- **Remaining budget** — shown clearly, goes red if you've gone over

### Usability
- **Filter by category** — tap a category tab to see only those expenses
- **Multi-currency** — choose from ₹ INR, $ USD, € EUR, £ GBP, ¥ JPY before locking the trip
- **Settings** — update trip name or duration after locking, without resetting everything
- **Toast notifications** — feedback on every action without browser alerts interrupting flow
- **Install as app** — installable on Android and iOS via the browser's "Add to Home Screen"

---

## Getting Started

### Run locally

Just open `index.html` in a browser. No build step, no dependencies, no server required for basic use.

For PWA features (offline caching, installability), serve it over a local or remote server:

```bash
# Python
python -m http.server 8080

# Node
npx serve .
```

Then open `http://localhost:8080` in your browser.

### Deploy

Drop the three files onto any static host (GitHub Pages, Netlify, Vercel, Cloudflare Pages). No backend needed.

```
index.html
manifest.json
service-worker.js
icon-192.png      ← add your own icons
icon-512.png      ← add your own icons
```

> **Note:** For PWA install to work, the app must be served over HTTPS (or localhost).

---

## How to Use

1. Open the app and fill in your **trip name**, **total budget**, **number of days**, and **currency**
2. Hit **Lock Budget & Start Trip**
3. As you spend, tap **Add Expense** — enter what it was, how much, which day of the trip, and the category
4. Check the stats and category breakdown to see how you're tracking
5. Use **Start New Trip** (↺ icon) when you're back and ready to reset for the next expedition

---

## File Structure

```
index.html          Main app — all HTML, CSS, and JS in one file
manifest.json       PWA manifest for installability
service-worker.js   Caches assets for offline use
```

All data is stored in `localStorage` — nothing is sent anywhere.

---

## Built With

- Vanilla HTML, CSS, JavaScript — no frameworks, no build tools
- [Sora](https://fonts.google.com/specimen/Sora) + [DM Mono](https://fonts.google.com/specimen/DM+Mono) via Google Fonts
- Web App Manifest + Service Worker for PWA support

---

## Limitations

- Data lives in the browser's `localStorage` — clearing site data will wipe it
- No sync across devices (by design — offline-first means no server)
- No export yet (planned: CSV download)

---

## Planned / Ideas

- [ ] CSV / PDF export of expense log
- [ ] Per-day budget allocation (set a daily limit, not just a total)
- [ ] Multiple trips stored simultaneously
- [ ] Shared trip mode (split expenses with a group)
- [ ] Dark/light theme toggle

---

## License

MIT — free to use, fork, and adapt for your own expeditions.

---

*Made during a trek when the mountains had better reception than the budget.*
