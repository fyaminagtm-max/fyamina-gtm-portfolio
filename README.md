# Fyamina Rout — GTM Engineer Portfolio

This is the exact current version of the portfolio, exported from Claude Artifacts.

## What this project is

The site is a single self-contained static page: `index.html` contains all markup,
CSS, and JavaScript inline (this is how it was built and published as a Claude
Artifact, and it has been exported here unchanged — nothing was split into
separate component files, rewritten, or simplified). Fonts (Cormorant Garamond,
Playfair Display, Inter, IBM Plex Mono) are loaded from Google Fonts via `<link>`
tags in the `<head>`, exactly as in the artifact — there are no local font files
or image assets to bundle, since none were used in the original build.

All current interactions are preserved as-is:
- Client-side routing between the homepage and each project's case-study view
  (hash-based, no external router)
- The interactive step-by-step workflow explorers (Beacon Health, Nursing
  Intelligence)
- Video placeholder components, document card, tech chips
- Dark/light theme support via `prefers-color-scheme`
- All copy, placeholders, and project structure

## Running locally

You need [Node.js](https://nodejs.org) installed (v18+ recommended).

```bash
npm install
npm run dev
```

Then open the local URL that's printed (defaults to `http://localhost:3000`).

There is no build step — `index.html` is served directly by a lightweight
static file server (`serve`), so what you see locally is exactly what will be
deployed.

## Deploying with GitHub + Vercel

1. Push this project to a new GitHub repository:
   ```bash
   git init
   git add .
   git commit -m "Initial commit — Fyamina Rout portfolio"
   git branch -M main
   git remote add origin <your-repo-url>
   git push -u origin main
   ```
2. Go to [vercel.com](https://vercel.com), click **New Project**, and import
   that GitHub repository.
3. Vercel will detect it as a static project (no framework, no build command
   needed — `vercel.json` in this project makes that explicit). Click **Deploy**.
4. Vercel will serve `index.html` at your project's root URL.

## Editing later

Everything — layout, copy, styles, interactions — lives in `index.html`. Since
it's plain HTML/CSS/JS with no build tooling, you can open it directly in
VS Code and edit it like any other web page; refresh the browser (or your
local `npm run dev` server) to see changes.
