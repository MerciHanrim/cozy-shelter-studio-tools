# Cozy Shelter · Card Studio

A single-file, browser-only tool for laying out artwork onto card templates and exporting print- or web-ready images. Nothing is uploaded anywhere — everything runs locally in your browser tab, and your source images are never modified or deleted.

**[Download `Cozy_Shelter_Card_Studio_v1.9.13.html`](Cozy_Shelter_Card_Studio_v1.9.13.html)** and open it in any modern browser (Chrome, Edge, Firefox). No install, no build step.

## Features

- **Image placement** — Cover (fills the frame, may crop edges) or Contain (keeps the whole image, may leave margins)
- **Card layout controls** — aspect ratio, bleed, and safe-area settings
- **Title styles** — Overlay Band (title on top of the image) or Frame Template (title in a dedicated area)
- **Front / back layouts** — front includes the title, back uses a dedicated back-side layout
- **Custom fonts** — add TTF / OTF / WOFF / WOFF2 files for the current session (via the FontFace API; re-add after closing the browser)
- **QA overlays** (preview only, never baked into the exported file)
  - Structure overlay — frame and section guides
  - Visual balance overlay — center axis, thirds grid, title baseline
  - Safe-area tint — highlights anything outside the safe area
- **Print-readiness badge** — automatically checks whether the export resolution meets 300dpi for the physical card size, with a full-sentence screen-reader announcement
- **Export formats** — PNG (crisp graphics), WebP (small size), JPEG (photos), with configurable output height
- **Accessibility** — default / color-vision-adjusted / high-contrast display modes, full keyboard support
- **Memory reset** — releases references to the current image and uploaded fonts (your files on disk are untouched)
- **Korean / English** UI toggle

## Privacy

All processing happens in-browser. No image, font, or project data is ever sent to a server.

## License

Original code © Hanrim · Cozy Shelter. All rights reserved — free to download and use as-is. No external JavaScript libraries are bundled; Google Fonts (SIL Open Font License) may be loaded for typography.

See the in-app **About · Usage** dialog for full attribution details.
