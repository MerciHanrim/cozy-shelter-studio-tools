# Cozy Shelter Studio · Tools

A small suite of single-file, browser-only tools built for the [Cozy Shelter](https://cozyshelter.tistory.com) blog's own production workflow, and shared here for anyone who finds them useful.

Every tool is one self-contained `.html` file: download it, double-click (or drag into your browser), and it runs entirely client-side. Nothing is ever uploaded to a server, and your source files are never modified or deleted.

## Tools

| Tool | What it does |
|---|---|
| [Card Studio](card-studio/) | Lay out artwork onto card templates (front/back, bleed, safe area) and export print- or web-ready images |
| [Image Studio](image-studio/) | Batch convert, optimize, and watermark images (lossless or web-optimized PNG, WebP, JPEG) |
| [Visual Review](visual-review/) | Rate, annotate, and compare large batches of images to pick favorites |
| [Lotus Studio](lotus-studio/) | Mind-map brainstorming tool built around the Lotus Blossom technique |
| [Reminder Studio](reminder-studio/) | Import a contacts CSV and get a ready-to-copy message for upcoming birthdays and anniversaries |

Each folder has its own README with the full feature list and license details.

## Why single HTML files

These tools are built to be downloaded once and used offline, indefinitely, without depending on a build toolchain, a package registry, or this repository staying online. That also means there's no shared codebase between them — each is independent, versioned, and updated on its own schedule.

## License

Original code in this repository is © Hanrim · Cozy Shelter. All rights reserved — free to download and use as-is; this is not an open-source project seeking contributions.

**Image Studio is one exception**: it embeds the [libimagequant](https://github.com/ImageOptim/libimagequant) PNG engine, which is licensed **GPL-3.0-or-later**. See [image-studio/README.md](image-studio/README.md) for the full breakdown of bundled third-party components and licenses.

**Reminder Studio is the other exception**: everything else in this suite makes zero network calls, but Reminder Studio has an *optional* AI-personalization feature — off by default — that, once you supply your own API key, calls Anthropic, OpenAI, Google, or xAI directly from your browser. See [reminder-studio/README.md](reminder-studio/README.md#privacy) for the full disclosure.

## Origin

These tools were designed and iterated on as part of writing the Cozy Shelter blog — see the individual blog posts for design notes, screenshots, and version history in context.
