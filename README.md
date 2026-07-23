# Heat Sheet Highlighter

Upload a swim meet heat sheet PDF, enter the swimmers or teams you want to
find, and get back a copy of the PDF with every match highlighted.

Everything runs **entirely in the browser** — the PDF is never uploaded to a
server. Text extraction is done with [pdf.js](https://mozilla.github.io/pdf.js/)
and the highlighted PDF is generated with [pdf-lib](https://pdf-lib.js.org/),
both loaded from a CDN. There is no backend and no build step.

## How it works

1. Drop in a heat sheet PDF (must have a real text layer — see Limitations).
2. Add one or more search terms (swimmer name, team name/abbreviation), each
   with its own highlight color.
3. Click **Highlight PDF**. The app scans every page, finds matches, and
   draws a highlight box behind each one.
4. Download the highlighted PDF.

## Running it locally

No install required — it's a single static HTML file.

```bash
# Just open it directly
open index.html        # macOS
start index.html        # Windows
xdg-open index.html     # Linux
