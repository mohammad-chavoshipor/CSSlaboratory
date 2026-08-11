<div align="center">

# CSS Laboratory

**An interactive, slide-based CSS course in a single HTML file.**

Live demo → **[css.mchavoshipor.ir](https://css.mchavoshipor.ir)**

[![Deploy](https://github.com/mohammad-chavoshipor/CSSlaboratory/actions/workflows/pages.yml/badge.svg)](https://github.com/mohammad-chavoshipor/CSSlaboratory/actions/workflows/pages.yml)
[![License: MIT](https://img.shields.io/badge/License-MIT-ffb454.svg)](LICENSE)
[![No build step](https://img.shields.io/badge/build-none-59c2ff.svg)](#running-locally)

</div>

---

## What this is

CSS Laboratory teaches CSS the way it is actually learned: by moving a slider and watching
a box move. Every concept comes with a live playground — change `justify-content`, drag a
`gap` slider, flip `position: absolute` — and the rendered result and the generated CSS
update side by side, immediately.

It is **one file**. No framework, no bundler, no `node_modules`, no build step. Open
`index.html` in a browser and the whole course runs.

> **Language:** the course content is written in **Persian (فارسی)** with a full RTL
> layout. All CSS property names, values and code samples are in English, so the
> playgrounds are usable regardless of the language you read.

## Contents

15 chapters, ordered so each one builds on the previous:

| # | Chapter | Covers |
|---|---------|--------|
| 1 | Anatomy of a CSS rule | selector, declaration block, property, value, specificity |
| 2 | Selectors | type, class, id, attribute, pseudo-class, pseudo-element, combinators |
| 3 | Units & colors | px / em / rem / %, vw / vh, `hex`, `rgb`, `hsl`, `oklch` |
| 4 | The box model | content, padding, border, margin, `box-sizing` |
| 5 | Typography | font stacks, size scale, line-height, letter-spacing, `text-wrap` |
| 6 | Flexbox lab | `flex-direction`, `justify-content`, `align-items`, `wrap`, `gap`, `flex-grow` |
| 7 | Grid lab | `grid-template-columns`, `fr`, `repeat()`, `minmax()`, areas, `gap` |
| 8 | Position | `static`, `relative`, `absolute`, `fixed`, `sticky`, `z-index` |
| 9 | Transform + transition | `translate`, `rotate`, `scale`, timing functions, duration |
| 10 | Animation & `@keyframes` | keyframe authoring, iteration, direction, fill mode |
| 11 | Responsive design | breakpoints, `clamp()`, container-aware layout, mobile-first |
| 12 | Custom properties & functions | `--vars`, `var()`, `calc()`, `min()` / `max()` / `clamp()` |
| 13 | Full property reference | searchable index of CSS properties |
| 14 | Copy-paste templates | ready-made layout and component snippets |
| 15 | Golden rules | the practical tips that make CSS click |

## Features

- **Live playgrounds** — sliders, toggles and dropdowns that mutate real elements in real time.
- **Generated code view** — the CSS you just produced, syntax-highlighted, ready to copy.
- **Slide navigation** — arrow keys, `Space`, `PageUp` / `PageDown`, `Home` / `End`, plus a table-of-contents drawer.
- **Property search** — type `flex` or `shadow` to jump straight to the relevant reference entry.
- **Accent themes** — amber, blue, purple, red and teal, switchable at runtime.
- **Full RTL support** — the layout is genuinely right-to-left, not a mirrored afterthought.
- **Zero dependencies** — the only network request is Google Fonts, and the page degrades gracefully to system fonts without it.
- **Responsive** — works from a phone screen up to a projector.

## Running locally

Clone and open. That is the whole procedure.

```bash
git clone https://github.com/mohammad-chavoshipor/CSSlaboratory.git
cd CSSlaboratory
open index.html          # macOS   (Linux: xdg-open, Windows: start)
```

If you prefer serving it over HTTP (recommended when you want to test with a phone on the
same network):

```bash
python3 -m http.server 8080
# then visit http://localhost:8080
```

## Project structure

```
CSSlaboratory/
├── index.html      # the entire application — markup, styles and scripts
├── CNAME           # custom domain for GitHub Pages
├── LICENSE         # MIT
├── README.md
└── .github/workflows/pages.yml   # publishes the site on every push to main
```

Everything lives in `index.html`, organised top to bottom as: design tokens (`:root`
custom properties) → base styles → component styles → slide markup → playground logic.
Editing a chapter means editing its `<section>` and the small script block that drives it.

## Deployment

The site is published with **GitHub Pages** via the `Deploy` workflow, served at the
custom domain `css.mchavoshipor.ir`. Every push to `main` uploads the repository as-is and
republishes it — there is nothing to compile.

## Contributing

Corrections, new chapters and better playgrounds are welcome. Because the project is a
single file, please keep changes scoped:

1. Match the surrounding style — the codebase uses compact CSS, design tokens from
   `:root`, and plain DOM APIs (no libraries).
2. Keep the file dependency-free. No CDN scripts, no build tooling.
3. Test in at least one Chromium browser and one Firefox before opening a pull request.

## License

[MIT](LICENSE) © Mohammad Chavoshipor
