# MD to PDF

A single-file, offline **Markdown-to-PDF editor** with a live, print-accurate preview.
Open one HTML file in your browser, write Markdown, tune the page, and use your
browser's **Save as PDF** to get a document that looks exactly like the preview.

- **Zero dependencies. Zero build. Zero network.** The whole app is one `index.html`.
- **Print-accurate preview** — the on-screen "sheet" mirrors the real page size, margins, and type, so what you see is what prints.
- **Private by design** — everything runs locally in your browser; nothing is uploaded.

---

## Quick start

No installation, no toolchain:

1. Download `index.html`.
2. Open it in any modern browser (double-click, or drag it onto a browser window).
3. Write Markdown in the editor and watch the preview update.
4. Click **Save as PDF** (or press <kbd>Ctrl/Cmd</kbd>+<kbd>S</kbd>) and, in the print
   dialog, choose **Save as PDF** as the destination.

> **Tip:** In the print dialog, leave margins on **Default** so the margins you set in
> the app are the ones used, and turn off headers/footers unless you want the date and
> file path on every page.

---

## Features

### Editing & files
- Live Markdown editor with word count and a debounced, flicker-free preview.
- **Open** `.md`/`.markdown`/`.txt` files, or **drag and drop** a file anywhere onto the window.
- **Save .md** to download your source, and **Save as PDF** via the browser print pipeline.
- Your document and settings are **auto-saved to `localStorage`**, so they survive a reload.
- <kbd>Tab</kbd> inserts two spaces in the editor.

### Page setup
- **Paper sizes:** A4, US Letter, US Legal, A5, A3, B5, Executive, Tabloid, Pocket book.
- **Orientation:** portrait / landscape (emitted as reliable `@page` rules so the PDF matches the preview).
- **Margins** in millimetres (independent sides / top-bottom).
- **Zoom:** fit-to-width or 50–150%.
- Optional **page-break guides** drawn over the preview.

### Typography
- Separate font choices for **body**, **headings**, and **code**, from curated system-font stacks
  (serif, sans-serif, monospace) — no web fonts, so documents render identically on any machine that has the fonts.
- Adjustable **size** (pt/px), **line height**, **paragraph spacing**, and **ink/accent colour**.
- **Ragged or justified** alignment, optional **hyphenation**, and an optional **table of contents**.

### Markdown support
Headings, **bold** / *italic* / ~~strikethrough~~ / `inline code`, links and images,
autolinks, blockquotes, fenced code blocks, tables (with column alignment), horizontal
rules, ordered/unordered/nested lists, and task boxes (`[x]` / `[ ]`).

**Explicit page breaks** — put any of these on their own line:

```
\pagebreak
[[newpage]]
<!-- pagebreak -->
```

Headings avoid being stranded at the foot of a page, and tables and code blocks avoid
being split across pages.

---

## Privacy & security

- **Fully offline.** The app makes no network requests. A Content-Security-Policy
  (`connect-src 'none'`, etc.) blocks any outbound connection as defense-in-depth.
- **URL sanitisation.** `javascript:`, `vbscript:`, `file:`, and non-image `data:` URLs
  in Markdown links/images are neutralised.
- **⚠️ Raw HTML is rendered as-is.** Inline HTML in your Markdown is passed through
  unchanged, so **only open `.md` files you trust.** A malicious file could run
  JavaScript in the page. (A stricter sanitising mode is on the roadmap — see
  [CONTRIBUTING.md](CONTRIBUTING.md).)

---

## Browser support

Any current version of Chrome, Edge, Firefox, or Safari. Chromium-based browsers give
the most faithful print output. In Firefox, if landscape orientation doesn't apply,
check the orientation setting in the print dialog.

---

## Project layout

```
md2pdf/
├── index.html        # the entire application (HTML + CSS + JS, organised into sections)
├── README.md
└── CONTRIBUTING.md
```

There is intentionally **no build step and no dependency tree** — see
[CONTRIBUTING.md](CONTRIBUTING.md) for how the single file is structured and how to work on it.

---

## Contributing

Contributions are welcome! Please read [CONTRIBUTING.md](CONTRIBUTING.md) for the project's
constraints (offline, single-file, no build), coding conventions, and how to test changes.

If this tool earns a place in your workflow:

- ⭐ **Star the repo:** https://github.com/njnur/md2pdf
- 👤 **Follow the author:** https://github.com/njnur
- ☕ **Buy me a coffee:** https://wise.com/pay/me/mdnurujjamann

---

## License

**Non-Commercial** — see [LICENSE](LICENSE). Copyright © 2026 njnur.

You may use, copy, modify, and share the software for **non-commercial** purposes
with attribution. **Commercial use requires a separate license** — contact the author
via https://github.com/njnur. This is a source-available license, not an OSI-approved
open-source license.
