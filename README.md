# Sticker/A4

[Русский](README.ru.md)

A small browser tool for laying out physical sticky notes on A4 and printing text onto them in two passes.

**Live:** https://stickers.kindcat.dev

## Quick start

1. Add **Sticker 76**, **Sticker 90**, or create a custom sticker type.
2. Place stickers on the virtual **A4 (210 × 297 mm)** sheet.
3. Select a sticker:
   - drag it to move it;
   - use the **lock** button when its position is final;
   - resize the text area with its handles;
   - drag the centre handle to move the whole text area.
4. Double-click inside the text area to edit text.
5. Use **Auto fit** if the text should shrink automatically to stay inside the text area.
6. Switch to **GUIDES** and print the placement outlines.
7. Stick the physical notes onto those outlines.
8. Switch to **CONTENT**, feed the same A4 sheet back into the printer, and print the text.
9. If the second pass is shifted, use the global printer **X/Y calibration** instead of moving every sticker.

The editor also supports tabs, monochrome symbols, millimetre snapping, custom sticker sizes, named layouts, JSON import/export, and RU/EN UI.

## Printing

For predictable physical dimensions, use:

- Paper: **A4**
- Scale: **100%**
- Margins: **None**
- Headers and footers: **Off**

Workflow:

**GUIDES → place physical stickers → CONTENT**

## Shortcuts

- **Ctrl+Z** — undo
- **Ctrl+Shift+Z** — redo
- **Ctrl+D** — duplicate selected sticker
- **Delete** — delete selected sticker
- **Ctrl+S** — save named layout
- **Ctrl+P** — print current pass

## Layouts and storage

There is no backend. Layouts, sticker types, and settings are stored in the browser's **localStorage**.

Another PC or browser starts with its own local state. Use:

- **Export JSON** — back up or move layouts;
- **Import JSON** — restore them on another device.

## Run locally

No build step is required.

```bash
python3 -m http.server 8080 --directory public
```

Then open:

```text
http://localhost:8080
```

## Cloudflare Workers

The repository includes `wrangler.jsonc` and can be deployed as static assets:

```bash
npx wrangler deploy
```

Production domain:

```text
stickers.kindcat.dev
```

## License

The Sticker/A4 application source is MIT licensed. `public/support.js` is a generated Claude Design / dc-runtime bundle and is excluded from the MIT grant; see `THIRD_PARTY_NOTICES.md`.
