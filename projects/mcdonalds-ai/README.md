# McDonald's Azerbaijan — Static AI Menu Recommendation Demo

This folder contains a browser-only version of the McDonald's Azerbaijan notebook demo.

## Run locally
Keep `index.html` and `data.json` in the same folder, then serve the folder with any static HTTP server. For example:

```bash
python -m http.server 8000
```

Open `http://localhost:8000`.

## Publish with GitHub Pages
1. Upload the contents of this folder to the repository directory you want to publish (for example, `mcdonalds-demo/`).
2. In the repository, open **Settings → Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**.
4. Select `main` and the folder containing `index.html` (`/root` or `/docs`, depending on where you placed the files).
5. Save and wait for GitHub Pages to publish.

No Python server, API key, paid hosting, or model inference backend is needed at runtime. Similarity scores are precomputed from the provided dataset using the notebook's method and run in the browser. Static GitHub Pages does not sleep like a free compute service, but no host can promise 100% uptime.

## Implemented notebook logic
- Product similarity uses only the `Main` category (29 items).
- Numeric features: Protein, Fat, Carbs, Energy.
- Missing numeric values are filled with the mean of the corresponding `Main`-category feature, then MinMax-scaled.
- Nutritional cosine similarity is averaged equally with TF-IDF cosine similarity for `Name + Allergens` (`stop_words='english'`).
- The top five results exclude the selected item, as in the notebook.
- The five recommendation cards are displayed in one aligned row on wide screens, with responsive layouts on smaller screens.
- Each generated menu displays the actual selected product names in its heading and as individual product cards.
- The menu builder uses all eight categories in the categorized CSV, filters by protein type for `Main`, supports the notebook's allergen exclusions, and attempts to generate five unique menus within ±100 kcal of the target (up to 5,000 random attempts).

## Dataset notes
- `mcdonalds_categorized_new.csv`: 216 rows, 10 columns; used as the app's full catalog and category source.
- `data_updated.csv`: 216 rows, 9 columns; its `Main` rows have matching product names and nutrition values to the categorized CSV. Some non-main rows differ, and the categorized file has cleaned names and category labels.
- Missing values exist in the source dataset. The app displays unavailable allergen/description/nutrition fields as not provided; it does not invent them.
- The original notebook's menu generator requires at least three selected items in total (despite its message saying "categories"). This same condition is retained.
- Allergen filtering is based on text in the dataset and is not a medical safety guarantee. Always verify allergen information with the restaurant.

## Files
- `index.html` — responsive interface and browser-side menu generation.
- `data.json` — catalog plus precomputed 29×29 similarity matrix.

## Model limitations
This is a static demo of the submitted notebook, not a retrained model. There is no user purchase history or collaborative-filtering matrix. Menu combinations are randomized within the notebook's calorie tolerance; the menu generator is not an optimization solver.
