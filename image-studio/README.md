# Cozy Shelter · Image Studio

A single-file, browser-only tool for batch converting, optimizing, and watermarking images. Nothing is uploaded anywhere — all processing happens locally in your browser tab, and your source files are never modified or deleted.

**[Download `Cozy_Shelter_Image_Studio_v5.0.18.html`](Cozy_Shelter_Image_Studio_v5.0.18.html)** and open it in any modern browser (Chrome, Edge, Firefox). No install, no build step.

## Features

- **Drag-and-drop files or folders**, with a batch queue you can add to across multiple drops
- **Input formats** — PNG, JPEG, WebP
- **Output formats** — keep original, or convert to WebP / JPEG
- **Quality control**, width-based resizing, and a per-file processing summary
- **Target file size (KB)** for JPEG/WebP output — auto-adjusts quality only (resolution untouched) to land under a size budget
- **PNG-specific modes**
  - Lossless (OxiPNG)
  - Web-optimized (libimagequant color quantization, processed in an isolated Worker)
- **Watermarking** — applied only to exported output; originals are never touched
  - Text watermark — custom text, saved/removable presets, searchable font picker with custom font upload, live font preview
  - Image watermark — PNG / WebP / JPEG files as a watermark
  - Text and image watermarks can be toggled independently and used together (e.g. bottom-left text credit + bottom-right signature image)
  - Shared controls: 9-point quick positioning, horizontal/vertical offset, size, opacity
- **Per-file download** or **batch ZIP download**
- **Accessibility** — default / color-vision-adjusted / high-contrast display modes
- **Open-source license notices** built into the app (see below)
- **Korean / English** UI toggle

## Privacy

All processing happens in-browser. No image is ever sent to a server.

## License

Original code © Hanrim · Cozy Shelter. All rights reserved — free to download and use as-is.

This tool bundles two third-party engines for PNG optimization, both disclosed in-app under **About · Open Source Licenses**:

| Component | License | Source |
|---|---|---|
| [@jsquash/oxipng](https://github.com/jamsinclair/jSquash) 2.3.0 (lossless PNG) | Apache-2.0 | full text included in-app |
| [libimagequant](https://github.com/ImageOptim/libimagequant) (web-optimized PNG, wrapper: MIT) | **GPL-3.0-or-later** | full text included in-app, linked to upstream source |

Because the libimagequant engine is embedded (as an isolated Worker payload) rather than merely linked, the GPL-3.0-or-later terms apply to that component as distributed here; the official license text and a link to the upstream project are included in the file's license dialog. JSZip (batch ZIP downloads) is loaded from a CDN reference (MIT license) and is not bundled. Google Fonts (SIL Open Font License) may be loaded for typography.
