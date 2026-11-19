<div align="center">

# Hacı Axundzadə · Portfolio

**Data Science · Machine Learning · AI · Software Development**

[![Website](https://img.shields.io/badge/Portfolio-Live-FFC928?style=for-the-badge&logo=githubpages&logoColor=111111)](https://hajye.github.io/)
[![GitHub](https://img.shields.io/badge/GitHub-haJye-181717?style=for-the-badge&logo=github)](https://github.com/haJye)

*A personal portfolio featuring selected projects, technical skills, experience, and experiments.*

</div>

---

## ✦ Overview

This repository contains the source code for my personal portfolio website. It brings together my background, technical interests, selected projects, and practical work in one place.

The website uses a **terminal- and Jupyter-inspired visual style**, with notebook-like sections and a responsive layout.

## ✦ What's inside

| Section | What you'll find |
| --- | --- |
| **About** | A short introduction and professional focus |
| **Skills** | Data & ML, backend, frontend, tools, and languages |
| **Experience & Education** | Work experience and academic background |
| **Projects** | Selected projects with visual previews and links |
| **Currently Learning** | Technologies and topics I am exploring |
| **GitHub Activity** | Repository statistics and recent public activity |
| **Contact** | Ways to get in touch |

## ✦ Featured projects

A selection of interactive and technical projects presented in the portfolio:

- **McDonald's Azerbaijan — AI Menu Recommendation**  
  A browser-based product recommendation and menu-generation demo using a precomputed item-similarity matrix, nutrition information, and allergen filters.
- **MovieLens**  
  A recommendation-system project based on the MovieLens dataset.
- **Solar System**  
  An interactive browser-based solar-system experience.

Visit the [live portfolio](https://hajye.github.io/) for project previews and additional details.

## ✦ Tech stack

- **Frontend:** HTML5, CSS3, JavaScript
- **Styling:** CSS Grid, Flexbox, custom properties, responsive media queries
- **Typography:** Google Fonts — Space Grotesk, Inter, JetBrains Mono
- **Project demos:** Standalone browser-based HTML/CSS/JavaScript where applicable

The portfolio itself does not require a frontend framework, build system, or package manager.

## ✦ Run locally

You can open the main page directly in a browser. For a local HTTP server, use:

```bash
git clone https://github.com/haJye/haJye.github.io.git
cd haJye.github.io

# Python 3
python -m http.server 8000
```

Then visit `http://localhost:8000`.

Some browser features may behave more reliably when served over HTTP rather than opened through a `file://` URL.

## ✦ Repository structure

```text
haJye.github.io/
├── index.html
├── projects/
│   ├── mcdonalds-ai/
│   │   ├── index.html
│   │   ├── data.json
│   │   ├── images/
│   │   ├── source-data/
│   │   └── README.md
│   ├── movielens/
│   └── solar-system/
├── images/
└── README.md
```

*The tree above highlights the main portfolio and project areas; individual asset files are omitted.*

## ✦ Add or update a project

1. Add the project files under `projects/<project-name>/`.
2. Add a project card to the projects section in the root `index.html`.
3. Include a concise description, relevant technologies, and a preview image or animation where available.
4. Verify the project locally before publishing.

Example project-card structure:

```html
<article class="panel project" data-category="data">
  <div class="project-media">
    <img src="PROJECT_PREVIEW.webp" alt="Project preview" loading="lazy">
  </div>
  <div class="project-meta">
    <span>Category</span>
    <span>Project</span>
  </div>
  <div class="project-body">
    <h3>Project title</h3>
    <div class="stack">
      <span>Python</span>
      <span>Machine Learning</span>
    </div>
    <p>A short and accurate project description.</p>
    <div class="project-links">
      <a href="PROJECT_URL" target="_blank" rel="noopener noreferrer">Explore →</a>
    </div>
  </div>
</article>
```

## ✦ Deployment

The website is designed to be hosted with **GitHub Pages**:

1. Open the repository's **Settings → Pages**.
2. Select **Deploy from a branch**.
3. Choose the `main` branch and `/ (root)` directory.
4. Save and wait for the deployment to complete.

The published website is available at [hajye.github.io](https://hajye.github.io/).

## ✦ Notes

- Project descriptions are intended to reflect the actual implementation; demos may have limitations documented in their own folders.
- The McDonald's recommendation demo uses precomputed similarity scores and does not use personal purchase history or live model inference.
- The McDonald's demo's allergen filtering is based on the available dataset and should not be treated as a medical safety guarantee.

---

<div align="center">

**Thanks for stopping by.**

© 2026 Hacı Axundzadə

</div>
