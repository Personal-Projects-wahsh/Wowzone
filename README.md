# WOW Zone — booking sample

A clickable prototype of the WOW Zone booking experience, built as a single
self-contained HTML file. No build step, no dependencies, no backend.

**Live:** https://personal-projects-wahsh.github.io/Wowzone/

## Views

The tab bar in the header switches between three views of the same simulated data:

| View | What it shows |
| --- | --- |
| **Website** | The guest-facing side: browse activities, pick a room, request a slot |
| **CR console** | The staff side: build proposals, load returning clients, send and confirm |
| **Calendar** | Room-by-room schedule with setup and reset time, and conflict detection |

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
