<div align="center">

# McDonald's Azerbaijan
### AI-Based Menu Recommendation Demo

**Content-based product similarity · Nutrition-aware menu generation · Allergen filtering**

[![Live Demo](https://img.shields.io/badge/Live%20Demo-Open-FFC928?style=for-the-badge&logo=googlechrome&logoColor=111111)](https://hajye.github.io/projects/mcdonalds-ai/)
[![Static App](https://img.shields.io/badge/Deployment-Static%20Web%20App-202020?style=for-the-badge)](#run-locally)

</div>

---

## Overview

This project is a browser-based demonstration of an AI-assisted menu recommendation approach for McDonald's Azerbaijan. It helps users explore similar menu items and generate meal combinations using the product catalogue, nutritional values, and allergen information available in the dataset.

The interface includes:

- Product selection with product image and detailed nutritional information.
- **Top 5 similar products**, including a compatibility score for each recommendation.
- Product descriptions, calories, protein, fat, carbohydrates, allergens, and category labels.
- A menu generator that creates combinations close to a selected calorie target.
- Responsive layouts for desktop, tablet, and mobile screens.

## How recommendations work

The demo uses a **precomputed item-to-item similarity matrix** generated from the notebook workflow. Similarity is calculated for products in the `Main` category.

### Features used

| Feature group | Input |
| --- | --- |
| Numerical | Protein, fat, carbohydrates, energy (kcal) |
| Text | Product name and allergen text |

### Processing steps

1. Missing numerical values for `Main` products are filled using the corresponding feature mean within that category.
2. Numerical features are scaled with MinMax scaling.
3. Cosine similarity is calculated for the nutritional feature vectors.
4. TF-IDF vectors are created from product names and allergen text, then compared using cosine similarity.
5. The two similarity matrices are combined with equal weighting.
6. The selected product is excluded and the five highest-scoring remaining products are displayed.

The compatibility percentage is a presentation of the computed similarity score. It should not be interpreted as a probability that a user will like or purchase the product.

## Menu generator

The menu generator uses products from the available catalogue categories and applies the configured allergen exclusions and calorie target.

- Main products can be filtered by protein type.
- The generator attempts to create up to five unique menus within a ±100 kcal range of the target.
- It uses randomized selection with a maximum of 5,000 attempts.
- It is a heuristic/randomized generator, not a mathematical optimization solver.

## Dataset

The application uses the following local data files:

| File | Contents |
| --- | --- |
| `data.json` | Product catalogue, category data, allergen values, and the precomputed 29 × 29 similarity matrix |
| `source-data/mcdonalds_categorized_new.csv` | 216 product records with 10 columns; categorized catalogue used by the app |
| `source-data/data_updated.csv` | 216 product records with 9 columns; source data used during preparation |
| `images/` | Local product images used by the interface |

Some source fields are missing. Where information is unavailable, the interface may display it as not provided rather than estimating or inventing a value.

## Run locally

No backend, API key, model server, or package installation is required to run the static demo.

From this directory, start a local server:

```bash
python -m http.server 8000
```

Then open:

```text
http://localhost:8000
```

Keep `index.html`, `data.json`, and the `images/` directory together so the application can load its local assets.

## Project files

```text
mcdonalds-ai/
├── index.html
├── data.json
├── images/
└── source-data/
    ├── mcdonalds_categorized_new.csv
    └── data_updated.csv
```

## Limitations and responsible use

- This is a static implementation of the notebook workflow; the model is not retrained in the browser.
- The demo has no user purchase history and does not implement collaborative filtering.
- Recommendations are item-to-item similarities, not personalized predictions based on an individual profile.
- Menu generation is randomized and constrained by the available catalogue and calorie range.
- Allergen filtering depends on the text recorded in the dataset. It is **not a medical safety guarantee**. Anyone with an allergy should confirm ingredient and cross-contact information directly with the restaurant.

---

<div align="center">

Part of the [Hacı Axundzadə portfolio](https://hajye.github.io/).

</div>
