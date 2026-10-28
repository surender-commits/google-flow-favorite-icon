
# Google Flow Favorite Icon Modification

A minimal Chrome extension that changes the background color of the favorite icon's status indicator container in Google Flow to black.

The extension uses a single CSS rule injected into matching Google Flow pages. It does not add buttons, keyboard shortcuts, or JavaScript functionality.

## Features

- **Black Background:** Sets the background color of `.status-indicators-container` to black.
- **Automatic Styling:** Applies the stylesheet automatically when a matching Google Flow page loads.
- **Lightweight:** Uses CSS only, with no JavaScript or background service worker.
- **Manifest V3:** Uses the Chrome Extension Manifest V3 format.
- **Minimal Configuration:** No popup, settings page, or user configuration is required.

## Project Structure

```text
google-flow-favorite-icon/
├── manifest.json
├── custom_style.css
└── icon.png
```

### File Overview

- `manifest.json` — Defines the extension metadata, icon, target website, and CSS content script.
- `custom_style.css` — Contains the CSS rule that sets the status indicator container's background to black.
- `icon.png` — Supplies the extension icon.

## Requirements

- Google Chrome or a compatible Chromium-based browser.
- Access to [Google Flow](https://flow.google.com/).

## Installation

1. Download or clone this repository.
2. Extract the ZIP archive if necessary.
3. Open `chrome://extensions/` in Chrome.
4. Enable **Developer mode**.
5. Click **Load unpacked**.
6. Select the extracted project folder containing `manifest.json`.
7. Open or reload Google Flow.

## How It Works

The extension injects `custom_style.css` into pages matching:

```text
https://flow.google.com/*
```

The stylesheet contains this rule:

```css
.status-indicators-container {
    background-color: black;
}
```

This changes the background color of elements using the `.status-indicators-container` class. The extension does not directly modify the favorite icon itself.

## Customization

To change the background color, edit `custom_style.css`:

```css
.status-indicators-container {
    background-color: black;
}
```

Replace `black` with another valid CSS color value, such as `#000000`, `#202020`, or `transparent`.

## Limitations

- The extension targets Google Flow only.
- It depends on the `.status-indicators-container` CSS class existing on the page.
- It changes the container background, not the icon's shape, color, or behavior.
- Google Flow interface updates may change the relevant class name or styling.
- No settings page or configurable options are included.

## Contributing

Contributions and suggestions are welcome. Test any CSS changes against the current Google Flow interface before submitting them.

## License

No license file is included in the supplied project.

Add a `LICENSE` file if you want to define the conditions for using, modifying, and redistributing this extension.
