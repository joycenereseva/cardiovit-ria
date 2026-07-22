# AGENTS.md

## Cursor Cloud specific instructions

### What this is
A purely static, client-side website (HTML + CSS + vanilla JS) — a personalized cardio/running workout protocol page for "Profª Joyce Neres". No backend, no database, no build step, and no package manager. State is persisted only in the browser's `localStorage`.

Key files: `index.html` (redirects to `cardio-exemplo.html`), `cardio-exemplo.html` (live demo page with the interactive interval timer), `cardio-template.html` (reusable template), `css/joyce-theme.css` (brand theme).

### Running / developing
- There is nothing to install or build. Serve the repo root with any static file server, e.g. `python3 -m http.server 8000` from `/workspace`, then open `http://localhost:8000/`.
- Opening files via `file://` also works, but a static server is preferred so the `index.html` → `cardio-exemplo.html` redirect and relative CSS path resolve cleanly.

### Non-obvious gotchas
- `cardio-exemplo.html` has an access-expiry lock screen (`#access-lock-screen`). It renders the real content only while the access date is valid (currently "Válido até 31/10/2026"). If testing after that date the page will show an expired/lock screen rather than the app.
- Tailwind CSS, Chart.js, and Google Fonts load from external CDNs. Without internet access the page still functions via `css/joyce-theme.css`, but styling, fonts, and the progress charts will be degraded.

### Lint / test / build
- No linters, test suite, or build tooling exist in this repo.
