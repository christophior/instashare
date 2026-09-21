# instashare

The project page for **instashare** — a small macOS app for sharing photographs to
Instagram from your Mac, built in 2019.

**The app is archived.** It is no longer developed, supported, or available for
purchase. This repository now serves only the static page that stands as a record
of the project, at [instashare.christophior.com](https://instashare.christophior.com).

## Development

The site is a single, dependency-free `index.html` — no build step, no package
manager, no frameworks. Edit it and open it, or serve the folder locally:

```
python3 -m http.server 8000
```

## Structure

```
index.html          the entire page, styles inline
favicon.svg         master icon (also used as the on-page logo)
favicon.ico         16/32/48px fallback for older browsers
apple-touch-icon.png 180px icon for iOS home screens
site.webmanifest    PWA manifest
assets/
  icon-192.png      manifest icon
  icon-512.png      manifest icon
  og-image.png      1200x630 link preview card
```

## Regenerating the icons

`favicon.svg` is the source of truth. The raster sizes are rendered from it —
any SVG rasterizer works, for example:

```
rsvg-convert -w 180 -h 180 favicon.svg -o apple-touch-icon.png
rsvg-convert -w 192 -h 192 favicon.svg -o assets/icon-192.png
rsvg-convert -w 512 -h 512 favicon.svg -o assets/icon-512.png
```
