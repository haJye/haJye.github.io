# Portfolio integration preview

This package combines the latest `index.html` from `haJye/haJye.github.io` with three standalone browser demos.

## Structure

- `index.html` — portfolio home page with three new **Live demo** links
- `projects/mcdonalds-ai/` — static McDonald’s menu recommendation demo + `data.json`
- `projects/movielens/` — browser-based MovieLens recommender lab
- `projects/solar-system/` — Three.js solar system simulation

## Local preview

Run a static server from this directory:

```bash
python -m http.server 8000
```

Open `http://localhost:8000`. The project demos are reachable from the portfolio project cards.

## Publish to the existing portfolio repository

No separate repository is required. The existing public repository is `haJye/haJye.github.io`, already configured as a GitHub Pages user site. Once you approve the preview, merge these paths into that repository:

1. Replace the root `index.html` with this package's `index.html`.
2. Add the `projects/` directory and all its contents.
3. Keep the existing `certificates/` directory and CV PDFs unchanged.
4. Do not change GitHub Pages settings; keep deployment from `main` / root.

The project demos are static and need no Python server at runtime. External network access is used for Three.js, MovieLens ZIP parsing, and Solar System textures. MovieLens CSV files are selected and processed locally in the visitor's browser; they are not uploaded.

## Important model notes

- McDonald’s: content-based hybrid item similarity; no purchase-history or user-level collaborative filtering. Allergen labels are not a medical safety guarantee.
- MovieLens: browser implementation is an interactive lightweight demonstration; reported Surprise/Keras notebook RMSE values are displayed as historical results, not re-trained in-browser. The demo accepts the official MovieLens latest-small dataset (about 1 MB) or CSV files.
- Solar System: visual orbital simulation, not an ephemeris-accurate astronomy engine.

## Validation

The package was checked for valid HTML structure, JavaScript syntax, relative project links, required data assets, and local HTTP serving. Full visual browser testing still depends on a real browser with network access.


## 2026-10-28 fixes
- McDonald's demo now serves 215 product images locally from `projects/mcdonalds-ai/images/`; product ID 130 has no supplied image.
- Solar System moon orbit paths now use `parent.mesh.position`, fixing the `Vector3.copy` runtime error.
