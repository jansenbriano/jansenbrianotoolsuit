# Jansen's Tool Suite

A single, self-contained web page that bundles four data-conversion tools behind one navbar. Everything lives in **`index.html`** — no build step, no install, no server. Open the file in a browser and use any tool.

## Tools

**Fleet Card Converter** — Converts fleet-card transaction `.txt` reports into Excel. Upload one or many files at once; it parses Payment and Top-Up reports with the same layout, merges them, removes duplicate rows, and sorts everything by date. Export is a single `.xlsx` (one sheet) or you can use **Copy Table** to copy the rows (no header) and paste them straight under an existing spreadsheet. Card-registration reports are detected and skipped automatically.

**DO Extractor** — Pulls and manages delivery-order data (Nopol / plate, vehicle type, client location) out of shipment logs, with an editable table.

**Data → Table** — Converts JSON, Excel files, or data copied from a spreadsheet into a structured "Rincian" table, and can convert the other direction to JSON.

**Rincian Harian** — Turns "Pengangkutan & Insentif" text into a structured table, with Download Excel, Download CSV, and copy-to-Excel.

## Features

- **One file.** All four tools are combined into a single `index.html` — readable, normal HTML/CSS/JS, no minified bundles.
- **Isolated apps.** Each tool's styles and scripts are scoped to its own panel, so they never collide even though they share element names.
- **Responsive.** The navbar adapts to desktop and mobile; on narrow screens the tabs collapse into a hamburger menu.
- **Light / dark mode.** A toggle in the navbar (desktop and mobile) switches the whole suite between themes and remembers your choice across reloads.

## Usage

1. Open `index.html` in any modern browser (double-click it, or drag it into a browser window).
2. Pick a tool from the navbar at the top.
3. Use the 🌙 / ☀️ button in the top-right to switch between dark and light mode.

> **Note:** The Excel/CSV import and export features rely on two libraries (SheetJS and PapaParse) loaded from a CDN, so those specific features need an internet connection. The pages themselves render and work offline.


## Built with

- Plain HTML, CSS, and JavaScript (no framework)
- [SheetJS / xlsx](https://sheetjs.com) — reading and writing Excel files
- [PapaParse](https://www.papaparse.com) — CSV/spreadsheet parsing
- IBM Plex Sans & Mono (Google Fonts) and Font Awesome icons

## Notes

- Element IDs are reused across the bundled tools; JavaScript access is scoped per panel so this is harmless in practice, though it means the markup contains intentional duplicate IDs.
- To change a tool's behavior, edit its scoped `<style data-app="…">` and `<script data-app="…">` blocks inside `index.html`.
