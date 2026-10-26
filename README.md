# Aidan Tack — Portfolio

Static portfolio site. Editor, photographer, marketer.

## Structure

```
index.html          Flat build — the deployed site, all sections in one page
support.js          Runtime
assets/web/         Photography, film stills, marketing images (re-encoded for web)
assets/film/        Reel video (reel-v2.mp4)
assets/             aidan-tack-resume.pdf
src/                Editable source components (.dc.html) — not served
```

`index.html` is the file hosts serve. `src/` holds the source components the site is
authored from; `src/Site.dc.html` is the full page, the others are its sections.

Note: image paths inside `src/*.dc.html` are written relative to the repo root
(`assets/web/…`), so previewing a file directly from inside `src/` will show missing
images. Serve from the root instead.

## Running locally

No build step. Serve the repo root over HTTP:

```
python3 -m http.server 8000
```

Then open `http://localhost:8000`.

Opening `index.html` via `file://` will not load the reel video or fonts correctly —
use a local server.

## Deploying

Any static host. No build command, no output directory — serve the repo root.

- **Vercel** — import the repo, framework preset "Other", leave build settings empty
- **Netlify** — publish directory `/`
- **GitHub Pages** — deploy from branch `main`, folder `/ (root)`

## Assets

All images are re-encoded for web delivery (quality 0.62 for photography, 0.72 for
marketing and film stills). Total payload is ~4.1 MB. Full-resolution originals are
kept outside this repo — replace files in `assets/web/` in place if you re-export.
