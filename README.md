# Contrastive Discovery — project page

Static project page for *Contrastive Discovery: Open-Ended Scientific Discovery over Competing Explanations*.
Plain HTML + CSS, no build step.

Live: https://www.biojameskim.me/contrastive-discovery/

## Files

| File | What to edit there |
|---|---|
| `index.html` | All text, authors, links, figure captions, BibTeX. Sections are marked with `<!-- ===== -->` banners; placeholders to fill are marked `<!-- EDIT -->`. |
| `style.css` | Colors, fonts, and column widths are variables at the top (`:root`). |
| `assets/*.png` | Figures. Replace a file with one of the same name, or change the `src` in `index.html`. |
| `.nojekyll` | Tells GitHub Pages to serve the files as-is. Keep it. |

All paths are relative, so the page works at any URL (localhost or `/<repo>/`).

## Run locally

```sh
python3 -m http.server 8000
# open http://localhost:8000/
```

To preview it under the same sub-path GitHub Pages uses, serve the parent folder instead
and open `http://localhost:8000/contrastive-discovery/`.

## Deploy

GitHub → repository **Settings → Pages → Build and deployment**: Source = *Deploy from a branch*,
Branch = `main`, folder = `/ (root)`. Every push to `main` redeploys within a minute or two.
Do **not** add a CNAME file here; the custom domain lives on the `biojameskim.github.io` repo and
project sites inherit it automatically.

## Regenerating figures from the paper PDFs

```sh
pdftoppm -png -r 200 -singlefile path/to/figure.pdf out && magick out.png -trim +repage assets/name.png
```
