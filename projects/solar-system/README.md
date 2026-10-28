# Solar System Simulation — Web Edition

A browser-based Three.js/WebGL adaptation of the original Pygame + PyOpenGL project. It preserves the core concept and controls while adding responsive UI and interactive camera navigation.

## Features
- Sun and all nine bodies from the original project (Mercury through Pluto)
- Textures loaded from the original repository's `textures2k` directory
- Earth satellites and Moon; Jupiter's four Galilean moons
- Saturn rings, asteroid belt, Halley and Encke elliptical comet paths
- Adjustable time scale, orbit visibility, labels, focus selector and camera reset
- Responsive desktop/mobile layout; no Python server or backend required

## Run locally
Open `index.html` through a local static server (recommended):

```bash
python -m http.server 8000
```

Then visit `http://localhost:8000`.

## GitHub Pages
Upload the contents of this folder to a project directory in a static GitHub Pages-enabled repository. No build step is required. The demo imports Three.js from unpkg and loads the original 2K textures from the `haJye/DSAI` repository, so the first load requires internet access.

## Notes
This is a browser rewrite, not a pixel-identical port. The original source uses 5 asteroid instances; this web adaptation uses a denser belt for a clearer 3D presentation. Orbital motion is visual/illustrative and not an ephemeris-accurate astronomical model.
