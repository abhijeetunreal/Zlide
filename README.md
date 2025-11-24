Zlide: Present Beyond Slides

Zlide is an infinite-canvas (not fully yet) presentation tool that lets you zoom through ideas instead of flipping slides. Create fluid storytelling journeys where every frame connects visually and conceptually. Zoom in, zoom out, explore—tell stories the way minds truly work.

---

## How Zlide Works

- **Infinite Canvas Engine**  
  The core `canvas` element in `index.html` defines a near-limitless coordinate plane. Every node—topics, media, callouts—is positioned relative to the global origin, so panning or zooming never hits a “slide edge.”

- **Zoom-Centric Navigation**  
  Interactions map mouse wheel + pinch gestures to a camera transform matrix. Scaling the matrix zooms in on details; scaling down reveals macro structure. Smooth easing keeps motion cinematic.

- **Semantic Frames**  
  Rather than discrete slides, content is grouped into frames with bounding boxes. Each frame can contain other frames, enabling nested storytelling (e.g., overview → chapter → scene → detail).

- **Path-Based Storytelling**  
  Story beats are stored as ordered waypoints (frame IDs + target zoom levels). Running a presentation traverses these waypoints, animating the camera between them for a choreographed narrative that still allows ad‑hoc exploration.

- **Data-Driven Rendering**  
  The presentation graph (frames, assets, transitions) is defined via JSON embedded in `index.html`. The renderer reads this schema at load, so any new content or layout tweaks require only data updates—no code edits.

---

## Authoring Workflow

1. **Define Scenes**  
   Add entries to the `frames` JSON array with coordinates, dimensions, labels, and child relationships.

2. **Attach Media**  
   Reference local or remote assets in each frame’s `content` block (text, SVG paths, images, or videos).

3. **Compose Story Paths**  
   Populate the `journeys` array with the presentation order, specifying target frame IDs and ideal zoom factors.

4. **Preview & Iterate**  
   Open `index.html` in any modern browser. Use scroll/trackpad to free-roam; press `Play Journey` (or the configured hotkey) to test the curated flow. Tweak JSON until motion and emphasis feel right.

---

## Key Concepts

- **Camera Transform**  
  `viewBox` manipulations on the SVG/canvas control global scale and translation.

- **Anchor Points**  
  Each frame stores an anchor that the camera focuses on when that frame becomes active.

- **Adaptive Typography**  
  Font sizes adjust relative to zoom so detail text remains legible without manual breakpoints.

- **Exploration Mode**  
  Presenters can break out of scripted journeys; the engine preserves current context and resumes the path seamlessly.

---

## Running Locally

1. Clone or download the repo.  
2. Open `index.html` directly in Chrome, Edge, or Firefox. No build step required.  
3. (Optional) Use `npx serve` or any static server for hot reload during edits.

---

## Contribution Guide

- Keep infrastructure agnostic—avoid domain-specific assumptions.  
- Store secrets (API keys, integrations) in `appsettings.json` per Vibe guidelines.  
- Favor data-driven enhancements; extend the JSON schema instead of hardcoding variations.  
- Submit PRs with short demos (GIF or Loom link) to showcase navigation changes.  
- Include tests or at least reproducible steps for interaction bugs.

---

## Roadmap Ideas

- Multi-presenter collaboration with live cursors.  
- Timeline scrubber to jump between keyframes.  
- AI-assisted layout suggestions for dense story nodes.  
- Export to interactive microsites.

---

## License

This project is part of the Vibe Open Source initiative—anyone is free to use, redistribute, and modify it with no limitations. Built with the passion of Vibe coding, it defaults to the root `LICENSE`; review that file if you need formal wording.

