# Heat Sheet Highlighter

Upload a swim meet heat sheet PDF, enter the swimmers or teams you want to
find, and get back a copy of the PDF with every match highlighted.

Everything runs **entirely in the browser** — the PDF is never uploaded to a
server. Text extraction is done with [pdf.js](https://mozilla.github.io/pdf.js/)
and the highlighted PDF is generated with [pdf-lib](https://pdf-lib.js.org/),
both loaded from a CDN. There is no backend and no build step.

## How it works

1. Drop in a heat sheet PDF (must have a real text layer — see Limitations).
2. The app scans the file for team names and lists them alphabetically in a
   searchable dropdown — start typing to filter, pick one, and click
   **Add team**. You can also type any swimmer name or team by hand.
3. Each entry gets its own highlight color.
4. Click **Highlight PDF**. The app scans every page, finds matches, and
   draws a highlight box behind each one.
5. Download the highlighted PDF.

## Running it locally

No install required — it's a single static HTML file.

```bash
# Just open it directly
open index.html        # macOS
start index.html        # Windows
xdg-open index.html     # Linux
```

## Running it on Replit

Import this repo into Replit and click **Run** — `.replit` serves the folder
with `python3 -m http.server`, so no Node install or build step is needed.

## Limitations

- Only text-based PDFs work — scanned/image-only heat sheets have no text
  layer for pdf.js to read, so nothing will match.
- Team auto-detection is a best-effort pattern match on the typical
  Hy-Tek / Meet Mobile "name … age … team … seed time" layout. Sheets with a
  different layout may find fewer teams (or none) — you can always type a
  team name manually in that case.
- Everything runs client-side, so very large PDFs (many pages) can take a
  little while to scan in-browser.
