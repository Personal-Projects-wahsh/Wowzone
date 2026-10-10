# WOW Zone — booking sample

A clickable prototype of the WOW Zone booking experience, built as a single
self-contained HTML file. No build step, no dependencies, no backend.

**Live:** https://personal-projects-wahsh.github.io/Wowzone/

## Views

The tab bar in the header switches between five views of the same simulated data:

| View | What it shows |
| --- | --- |
| **Website** | The guest-facing side: browse experiences by activity or space, describe a group and get suggestions, pick a slot and pay a deposit |
| **CR console** | The sales side: build a proposal, load a returning client, send it and confirm |
| **Calendar** | Operational day view per room, with setup and cleaning buffers, blended-room bookings and conflict markers |
| **Room operator** | On-the-day session screen: guest registration, check-in progress, staff needed and balance due |
| **Admin** | Dashboard of peak-day staffing gaps against a load threshold, plus revenue by activity |

## Scope of the sample

- Rooms, capacities and prices are **placeholders** standing in for the client's matrix.
- Payments are **simulated** — nothing is charged and no gateway is called.
- State lives in memory only, so **data resets on reload**.

## Running it locally

Open the file directly — no server needed:

```sh
open Wowzonebookingsample.html
```

Or serve the folder if you prefer a localhost URL:

```sh
python3 -m http.server 8000
# then visit http://localhost:8000/Wowzonebookingsample.html
```

## Deployment

Pushing to `main` triggers `.github/workflows/pages.yml`, which copies
`Wowzonebookingsample.html` to `index.html` and publishes it to GitHub Pages.
The single HTML file stays the only source of truth — the root `index.html` is
produced at build time rather than duplicated in the repo.
