# small-step

learning how to use github. intend to use github co-pilot x and enhance my user experience in any device by creating apps i need.

---

## Delta Plan 2100 — a guided walkthrough

A mobile web app that walks you through the **Bangladesh Delta Plan 2100** in 23 short steps —
from why the country needs a 100-year water plan, through the six hotspots, the challenges, the
vision and goals, every strategy, the investment plan and the governance arrangements.

Built with **nothing but HTML and CSS**. No JavaScript, no frameworks, no build step, no external
requests — not even a web font. It's a folder of files that a browser opens.

### How to open it

**On your phone or computer, from the files:** open `index.html` in any browser. That's it.

**Served locally** (useful if you want to test it exactly as it will be deployed):

```sh
python3 -m http.server 8000
# then visit http://localhost:8000
```

### How to publish it

The repo is already set up for GitHub Pages. One manual step is needed, because repository
settings can't be changed from a commit:

1. Go to **Settings → Pages** in this repository.
2. Under **Source**, choose either:
   - **GitHub Actions** — uses `.github/workflows/pages.yml`, which deploys on every push to `main`; or
   - **Deploy from a branch** → `main` / `(root)` — no workflow involved, since the site lives at the repo root.
3. The app goes live at **https://1adnansaad.github.io/small-step/**

Open that URL on Android and use Chrome's **Add to Home screen** if you want it as an icon.

### What's in here

```
index.html                     cover screen and full contents
assets/style.css               the single stylesheet — all layout, theming and components
chapters/01-overview.html      step 1
   …                           …
chapters/23-governance.html    step 23
chapters/24-recap.html         the finish screen
.github/workflows/pages.yml    GitHub Pages deployment
.nojekyll                      tells Pages to serve the files as-is
```

Each chapter is a self-contained page: a sticky header with the step counter, the content, and a
sticky Prev / Next bar at the bottom. Because every step is a real page, the Android back button
works the way you'd expect.

### Design notes

- Mobile-first, sized for ~360–412px screens, scales up on tablets and desktop.
- Automatic light and dark themes via `prefers-color-scheme`.
- Respects Android gesture bars (`env(safe-area-inset-bottom)`) and reduced-motion preferences.
- Charts are CSS bars; hotspot icons are inline SVG. No image files anywhere.

### Source

All content, figures and quotations come from **Bangladesh Delta Plan 2100 — Abridged Version
(English)**, General Economics Division (GED), Bangladesh Planning Commission, Government of the
People's Republic of Bangladesh.

This app is an unofficial reading aid, not a government publication.
