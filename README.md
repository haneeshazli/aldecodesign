# Aldecodesign

Website for **AL Decodesign** — interior design and renovation in Dengkil, Selangor.

The site is a single self-contained `index.html`: images, fonts and the page
runtime are embedded in the file, so there is no build step. React and ReactDOM
are the only external dependencies, loaded from unpkg.

## Deployment

| Version | GitHub Pages | Vercel |
| --- | --- | --- |
| Current (v3) | https://haneeshazli.github.io/aldecodesign/ | https://aldecodesign.vercel.app |
| V2 (editorial) | https://haneeshazli.github.io/aldecodesign/v2/ | https://aldecodesign.vercel.app/v2/ |

`index.html` is the current design. `v2/index.html` is a separate editorial
design — a different layout, not an iteration of the current one.

GitHub Pages serves the `main` branch root. Pushing to `main` publishes the site.

`index.html` is a copy of the editorial export kept alongside it as the working
source; edit the export, then copy it over `index.html` to publish.

## Local preview

```bash
python3 -m http.server 8000
```

Then open http://localhost:8000
