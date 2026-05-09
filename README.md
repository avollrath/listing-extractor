# Tori Listing Scraper

A lightweight browser extension for scraping listing results from [Tori.fi](https://www.tori.fi/) search pages.

The extension injects a floating scraper button directly into Tori search result pages and allows you to collect listings across multiple pages into a clean exportable table.

---

## Features

- Scrapes listings directly from Tori.fi search pages
- Supports multi-page scraping via automatic pagination
- Floating in-page UI
- Dark modal overlay with clean table layout
- Plain text export
- CSV export
- One-click clipboard copy
- Opens listing URLs directly from the table
- Deduplicates listings across pages
- Runs entirely locally in the browser

---

## Scraped Fields

The extension extracts:

- Listing title
- Brand / make (when available)
- Price
- Listing URL

---

## Supported Pages

Works on:

- Tori.fi search result pages
- Recommerce listing pages

Does **not** run on individual item pages.

Examples:

```txt
https://www.tori.fi/recommerce/forsale
https://www.tori.fi/recommerce/forsale?product_category=...
```

---

## Installation

### Chrome / Edge (Developer Mode)

1. Clone or download this repository
2. Open your browser extensions page:

#### Chrome

```txt
chrome://extensions
```

#### Edge

```txt
edge://extensions
```

3. Enable **Developer Mode**
4. Click **Load unpacked**
5. Select the extension folder

The extension will now activate automatically on supported Tori.fi pages.

---

## Usage

1. Open a supported Tori.fi search page
2. Click the floating:

```txt
📋 Scrape Listings
```

button in the bottom-left corner

3. The extension will:

- Scrape the current page
- Follow pagination automatically
- Collect listings from all pages
- Display the results in a modal overlay

4. Export options:

- **Copy CSV**
- **Copy Text**

---

## Multi-Page Scraping

The extension automatically follows Tori pagination using the page navigation links.

It continues scraping until no further `next page` link exists.

Listings are deduplicated automatically.

---

## Privacy

This extension runs entirely in your browser.

- No analytics
- No tracking
- No external servers
- No uploaded data

All scraping and processing happens locally on your machine.

---

## Project Structure

```txt
.
├── manifest.json
├── content.js
└── README.md
```

### Main Files

| File | Description |
|---|---|
| `manifest.json` | Extension configuration |
| `content.js` | Main scraper and UI logic |

---

## Technical Notes

The scraper currently relies on Tori.fi DOM selectors such as:

- `article.sf-search-ad`
- `a[rel="next"]`

If Tori changes its layout or CSS structure, the scraper may require updates.

---

## Limitations

- Depends on the current Tori.fi page structure
- Dynamic loading changes on Tori may affect scraping reliability
- Some listings may not contain all metadata fields
- Large result sets may take a few seconds to scrape

---

## Screenshots

### Floating Scraper Button

_Add screenshot here_

### Table View

_Add screenshot here_

### Plain Text Export

_Add screenshot here_

---

## Development

The extension is intentionally lightweight and framework-free.

### Tech Stack

- Vanilla JavaScript
- DOM parsing
- Browser content scripts
- Clipboard API

---

## License

MIT

---

## Disclaimer

This project is an independent utility and is not affiliated with or endorsed by Tori.fi.