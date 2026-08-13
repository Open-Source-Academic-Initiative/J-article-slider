# Article Slider (`mod_article_slider`)

A lightweight **Joomla 5** site module that displays a horizontal, responsive
row of hand-picked articles as cards ("related / suggested articles"), with a
**Load more** control. Built and maintained by the
[Open Source Academic Initiative (OpenSAI)](https://opensai.org).

## Features

- Show a curated set of articles chosen explicitly by **article ID**.
- Optional **random order**, or fixed order matching the ID list.
- Responsive Bootstrap card layout with lazy-loaded images.
- Progressive **Load more** reveal (3 cards at a time).
- Image resolution: uses the article's Schema.org thumbnail when present,
  otherwise falls back to the Joomla intro image.

## Requirements

- Joomla **5.x** (uses the namespaced module / dispatcher architecture)
- PHP **8.1+**

## Installation

**From a packaged zip**
1. Build a zip of this repository's contents (the manifest `mod_article_slider.xml`
   must sit at the zip root).
2. In Joomla admin: **System → Install → Extensions → Upload Package File** and
   drop the zip.

**From source (development)**
1. Copy the module files into `<joomla_root>/modules/mod_article_slider/`.
2. In Joomla admin: **System → Install → Discover**, then discover-install
   *Article Slider*.

After installing, create an instance under **Content → Site Modules → New →
Article Slider**, assign it a position, and publish it.

## Configuration

| Setting | Description |
|---|---|
| **Article ID's** | Comma-separated list of article IDs to display, e.g. `12,7,45`. |
| **Random Order?** | If enabled, cards are shown in random order; otherwise they follow the ID list order. |

## Repository layout

| Path | Purpose |
|---|---|
| `mod_article_slider.xml` | Extension manifest (metadata, params, file list) |
| `services/provider.php` | Joomla 5 DI service provider |
| `src/Dispatcher/` | Module dispatcher (entry point) |
| `src/Helper/` | Article fetch + helper logic |
| `tmpl/default.php` | Output template (card layout + Load-more) |

## Author & License

- **Author:** David Toro Triana — dtorot@opensai.org
- **License:** [GNU General Public License v3.0 or later](LICENSE)

© 2026 Open Source Academic Initiative (OpenSAI).
