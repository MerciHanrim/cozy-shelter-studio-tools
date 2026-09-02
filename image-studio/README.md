# Cozy Shelter · Image Studio

A single-file, browser-only tool for batch converting, optimizing, and watermarking images. Nothing is uploaded anywhere — all processing happens locally in your browser tab, and your source files are never modified or deleted.

**[Download `Cozy_Shelter_Image_Studio_v5.0.20.html`](Cozy_Shelter_Image_Studio_v5.0.20.html)** and open it in any modern browser (Chrome, Edge, Firefox). No install, no build step.

## Features

- **Drag-and-drop files or folders**, with a batch queue you can add to across multiple drops
- **Input formats** — PNG, JPEG, WebP
- **Output formats** — smart optimization / keep original format and re-encode / convert to WebP, JPEG, or PNG
- **Quality control**, longest-edge or width-based resizing, and a per-file processing summary
- **Target file size (KB)** for JPEG/WebP output — auto-adjusts quality only (resolution untouched) to land under a size budget
- **PNG-specific modes**
  - Lossless (OxiPNG)
  - Web-optimized (libimagequant color quantization, processed in an isolated Worker)
- **Watermarking** — applied only to exported output; originals are never touched
  - Text watermark — custom text, saved/removable presets, searchable font picker with custom font upload, live font preview
  - Image watermark — PNG / WebP / JPEG files as a watermark
  - Text and image watermarks can be toggled independently and used together (e.g. bottom-left text credit + bottom-right signature image)
  - Shared controls: 9-point quick positioning, horizontal/vertical offset, size, opacity
  - **Per-image watermark override** — optionally customize text/image watermark enable state, placement, size, opacity, and other appearance settings for individual images while the rest of the batch keeps the shared global configuration
  - The selected image watermark file itself remains shared across the batch; per-image overrides adjust how that watermark is applied rather than choosing a different source watermark image for each file
  - The default workflow remains batch-oriented. Per-image customization is optional and only used when individual images require different watermark placement or appearance.
- **Per-file download** or **batch ZIP download**
  - Each result's download action is a clearly labeled **"↓ Download"** button, visually separated from processing info
  - Exported filenames automatically get an **`-optimized`** suffix before the extension (e.g. `photo.png` → `photo-optimized.png`), matching the naming used inside ZIP downloads
- **Accessibility** — default / color-vision-adjusted / high-contrast display modes
- **Open-source license notices** built into the app (see below)
- **Korean / English** UI toggle

## Updates

### v5.0.20

- **Per-image watermark override** — Individual images can now override text/image watermark enable state, placement, size, opacity, and appearance while the rest of the batch continues to use the shared global configuration.
- **Global + Override workflow** — Keep the simplicity of batch processing while allowing exceptions only where needed.
- **Improved watermark workflow** — Select an image from the result list, switch between global and per-image settings, and remove an override at any time to return that image to the shared configuration.
- **Shared watermark asset** — Image-watermark placement and appearance can be overridden per image, while the selected watermark image file itself remains shared across the batch.

### v5.0.19

- **Clearer per-file download button** — replaced the icon-only control with a labeled **"↓ Download"** button, separated from the result's processing info.
- **Export filename marking** — downloaded files (individual and ZIP) automatically get an **`-optimized`** suffix before the extension (e.g. `photo.png` → `photo-optimized.png`).

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
