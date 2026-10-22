# Form3D — React website

A responsive React website for Form3D, Lebanon, with exactly three pages: **Home, Portfolio, and Christmas**. The package includes editable source and a ready-to-open static build. Everything is delivered locally; nothing is published automatically.

## Open the website

Open **`dist/index.html`** in a modern browser. No installation is needed to use the included build. Keep the whole `dist` folder together so its navigation, images, scripts, and styles remain available.

A local server gives more consistent browser session behavior across the three pages. To use one, install the development dependencies below, then run `npm run preview`.

## Edit and build

Requires **Node.js 20 or later** and npm. Open a terminal in this project folder:

```sh
npm ci
npm run dev
```

Open **http://127.0.0.1:4173**. The development command rebuilds when source files change; refresh the browser to see the result.

| Command | Purpose |
| --- | --- |
| `npm run dev` | Build and serve locally, rebuilding after edits |
| `npm run build` | Create the complete website in `dist` |
| `npm run check` | Check the current build's pages, assets, links, configuration, and key accessibility markup |
| `npm run preview` | Serve the existing `dist` build locally |

The build includes prerendered HTML and a bundled React application, so the supplied pages can also be opened directly from disk. Automated checks do not replace visual or device testing.

## Configure contact details

Edit **`public/config.js`**, replace `whatsappNumber` with the studio's international number, then run **`npm run build`**. Include the country code; digits only are preferred. A leading plus, spaces, parentheses, dots, and hyphens are normalized.

All general WhatsApp contact links and Christmas orders use this one setting. Christmas orders include the selected item's name in a prepared message; the visitor chooses whether to send it. Until a valid number is entered, the website shows a contact notice with the custom-design form.

For a static-only copy, edit **`dist/config.js`** directly. A later build replaces that file with `public/config.js`, so keep permanent changes in the source setting.

The same configuration contains the supplied Google Form link and the reserved `item1ModelUrl` setting.

## Project layout

```text
src/
  pages/           Home, Portfolio, Christmas
  components/      Shared navigation, viewers, contact and motion
  styles/          Base, pages, silhouette masks and showroom theme
  data.js          Product records and image descriptions
public/
  config.js        Studio settings
  assets/images/   Original images and responsive WebP variants
scripts/           Build, preview and output checks
dist/              Ready-to-open website
```

## Images and interactions

- Original product photographs and the original logo are retained. Responsive WebP copies preserve the complete image and its proportions.
- No Item 2 was supplied. Home uses **Item 4 alongside Item 3**, as approved.
- Item 1 is an accurately labeled **front/back two-photograph preview**, with flip controls and enlargement. No unseen geometry is invented.
- A genuine GLB/GLTF viewer can later be integrated at the `TwoViewPreview` boundary in `src/pages/Portfolio.jsx`, using `item1ModelUrl`. Setting that URL alone does not enable a 360° model.
- The Home introduction includes Skip and runs once per session. Reduced-motion preferences bypass it. The footer can pause decorative effects.
- Product viewers support keyboard controls, Escape, touch swipes, zoom, and focus restoration. Mobile and reduced-motion layouts use ordinary scrolling instead of the desktop pinned showcase.
- Dedicated product-order actions appear only on Christmas; general WhatsApp contact appears on every page.

## Showroom update — October 2026

The palette comes from median interior lettering pixels in the original `logo.png`: navy **#192C44**, turquoise **#4FD5D2**, with metallic gray **#C1C1C3** from its background. Backgrounds, controls, typography accents and seasonal effects use these colors and their tonal variations. The product photographs retain their own original colors.

`src/styles/showroom.css` contains the shared theme and responsive product sizing. Phone showcase/gallery images use 66% of their content width; the two-view preview uses 68%. Christmas keeps a compact two-column grid with images at 70% of each column. Product transforms stay within their smaller mobile stages. Enlarging a photograph intentionally opens a larger, zoomable view.

`src/styles/product-masks.css` contains inline SVG silhouettes traced from the photographs' flat outer backgrounds. Masks follow each original image's aspect ratio and work without external requests, including when opening the build directly from disk. They only hide the outer matte; original photographs, interior details and product colors are unchanged. The white-background house has a subpixel edge treatment to soften the matte fringe. The full Christmas collection and workshop photographs keep their complete photographic scenes.

No interaction component was replaced: the entrance animation, tilt, pinned desktop showcase, scroll reveals, front/back flip, viewer, contact settings and seasonal orders remain in place. Reduced-motion rules and the pause control are retained.
