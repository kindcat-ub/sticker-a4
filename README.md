# Sticker/A4

A tiny browser tool for printing text onto physical sticky notes and labels without having to write on them by hand.

## What it does

Sticker/A4 uses a two-pass print workflow:

1. Arrange sticker presets on a virtual **A4 (210 × 297 mm)** sheet.
2. Print faint **GUIDES** showing where to place the physical stickers.
3. Stick the notes onto the printed guide sheet.
4. Add text, tabs, and monochrome symbols inside each sticker's configurable text area.
5. Reinsert the same A4 sheet and print the **CONTENT** pass.

The editor also includes:

- reusable sticker presets and custom sizes;
- per-sticker printable-area margins;
- drag/drop positioning and millimetre snapping;
- inline text editing by double click;
- tab characters and monochrome semantic symbols;
- font, size, alignment, and line-height controls;
- printer X/Y calibration;
- guide brightness control;
- named layouts stored in `localStorage`;
- JSON import/export for backups;
- installable PWA shell and offline access after the first successful load.

## Run locally

No build step is required.

You can open `public/index.html` directly, or serve the folder locally:

```bash
python3 -m http.server 8080 --directory public
```

Then open `http://localhost:8080`.

## Printing

For predictable physical dimensions, use:

- Paper: **A4**
- Scale: **100%**
- Margins: **None**
- Headers and footers: **Off**

If your printer shifts repeated passes slightly, use the built-in X/Y calibration instead of moving every sticker.

## Cloudflare Workers static deployment

The repository includes `wrangler.jsonc` and can be deployed as a static-assets Worker.

```bash
npx wrangler deploy
```

For Git-based deployment, connect this repository in **Cloudflare → Workers & Pages → Create application → Continue with GitHub**. The Worker name is `sticker-a4` and must match the `name` in `wrangler.jsonc`.

Intended custom domain:

`stickers.kindcat.dev`

## Storage and privacy

There is no backend. Layouts and sticker presets stay in the browser's `localStorage` unless you explicitly export them as JSON.

## License

The Sticker/A4 application source is MIT licensed. `public/support.js` is a generated Claude Design / dc-runtime bundle and is excluded from the MIT grant; see `THIRD_PARTY_NOTICES.md`.