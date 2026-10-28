# MovieLens Recommendation Lab — Static Web Demo

A browser-only companion demo for the MovieLens recommender-system project. It is designed for GitHub Pages and does not require a Python backend, API key, or paid hosting.

## Run
Open `index.html` through a static server (recommended):

```bash
python -m http.server 8000
```

Then visit `http://localhost:8000`.

## Dataset
Download the official [MovieLens latest-small ZIP](https://files.grouplens.org/datasets/movielens/ml-latest-small.zip) from GroupLens. The ZIP is about 1 MB and contains `ratings.csv` and `movies.csv`. Select the ZIP in the demo, or select the two CSV files separately. The page reads the files in the browser; it does not upload them to a server. ZIP extraction uses JSZip from jsDelivr, so ZIP loading requires internet access. CSV loading works without JSZip.

The notebook's observed dataset dimensions (100,836 ratings, 610 users and 9,742 movies) correspond to MovieLens latest-small. This is distinct from any larger local archive the project owner may have.

## Interactive methods
- User-based collaborative filtering: Pearson correlation between users, top-neighbour weighted deviations from neighbour means.
- Item-based collaborative filtering: aggregate adjusted ratings across co-rated items/users.
- Popularity baseline: Bayesian weighted average of mean rating and a 3.5 prior.

These are lightweight browser implementations for an interactive demonstration. They are not a claim that the original notebook's trained Surprise/Keras models are running in the browser.

## Original notebook results
The evaluation panel displays the reported RMSE values from the original notebook: tuned Surprise SVD 0.863567, baseline SVD about 0.8734, KNNBasic/MSD about 0.9415, NMF about 0.9237, Keras dense model about 0.8936 and Keras dot-product model about 1.2237. They are reference results, not recomputed by this static demo.

## Publish on GitHub Pages
Upload the contents of this folder into a directory in the portfolio repository when all projects are approved. Enable GitHub Pages for the repository. No backend or scheduled process is needed.
