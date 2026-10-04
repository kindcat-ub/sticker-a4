# Sticker/A4

A small browser tool for laying out physical sticky notes on A4 and printing text onto them in two passes.

**Live:** https://stickers.kindcat.dev

## Quick start

1. Add **Sticker 76**, **Sticker 90**, or create a custom type.
2. Place stickers on the virtual A4 sheet. Use snap if you want exact millimetre positioning.
3. Select a sticker:
   - drag the outer sticker to move it;
   - use the **lock** button when its position is final;
   - drag the text-area handles to resize it;
   - drag the centre handle to move the whole text area.
4. Double-click inside the text area to edit text. Tabs and monochrome symbols are supported. **Auto fit** shrinks the font when needed so the text stays inside the text area.
5. Switch to **GUIDES** and print the placement outlines.
6. Stick the physical notes onto those outlines.
7. Switch to **CONTENT**, feed the same A4 sheet back into the printer, and print the text.
8. If the second pass is shifted, use the global printer **X/Y calibration** instead of moving every sticker.

Useful shortcuts:

- **Ctrl+Z** — undo
- **Ctrl+Shift+Z** — redo
- **Ctrl+D** — duplicate sticker
- **Delete** — delete selected sticker
- **Ctrl+S** — save named layout
- **Ctrl+P** — print current pass

## Печать

Для совпадения размеров в диалоге печати выставьте:

- Paper: **A4**
- Scale: **100%**
- Margins: **None**
- Headers and footers: **Off**

Workflow простой:

**GUIDES → наклеить стикеры → CONTENT**

Если повторная подача бумаги даёт смещение, используйте встроенную X/Y-калибровку принтера.

## Layouts and storage

There is no backend. Layouts, sticker types and settings are stored in the browser's **localStorage**.

That means another PC or browser starts with its own local state. Use:

- **Export JSON** — backup or move your layouts;
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
