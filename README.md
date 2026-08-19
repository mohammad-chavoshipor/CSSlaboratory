<div align="center">

# CSS Laboratory

**A slide-based CSS course plus step-by-step project exercises — in a single HTML file.**

Live demo → **[css.mchavoshipor.ir](https://css.mchavoshipor.ir)**

[![Deploy](https://github.com/mohammad-chavoshipor/CSSlaboratory/actions/workflows/pages.yml/badge.svg)](https://github.com/mohammad-chavoshipor/CSSlaboratory/actions/workflows/pages.yml)
[![License: MIT](https://img.shields.io/badge/License-MIT-ffb454.svg)](LICENSE)
[![No build step](https://img.shields.io/badge/build-none-59c2ff.svg)](#running-locally)

</div>

---

## What this is

CSS Laboratory teaches CSS the way it is actually learned: by moving a slider and watching
a box move, then by building a real page one step at a time.

The app has **two separate modes**, switchable from the top bar:

| Mode | What it is |
|------|------------|
| **دوره · Course** | 22 short lessons. Each opens with a one-sentence plain-language analogy, then a live playground. |
| **تمرین‌ها · Exercises** | 4 guided projects, 32 steps total. Pick a project, follow the steps, watch the page build itself in a live preview. |

Exercise content is deliberately kept **out of** the lessons: lessons explain a concept,
exercises apply several concepts to a finished page. Lesson 14 is a signpost that hands the
reader off to Exercise 1 at the right moment, and the reader can come back afterwards.

It is **one file**. No framework, no bundler, no `node_modules`, no build step. Open
`index.html` in a browser and everything runs.

> **Language:** the content is written in **Persian (فارسی)** with a full RTL layout. All CSS
> property names, values and code samples are in English, so the playgrounds are usable
> regardless of the language you read.

## The course

22 lessons, ordered so each builds on the previous. Every lesson starts with a
«به زبان ساده» box — the concept explained in one sentence, with a concrete analogy — before
any syntax appears.

| # | Lesson | Live playground |
|---|--------|-----------------|
| 1 | Cover | self-typing editor |
| 2 | What CSS actually does | — |
| 3 | Anatomy of a rule | — |
| 4 | Selectors | hover demo |
| 5 | Which rule wins (specificity) | toggle rules, see the winner and its score |
| 6 | Units: px / rem / % / vw | change the root font size, watch which bars move |
| 7 | Colors | HSL sliders → hex |
| 8 | `display` | block / inline / inline-block / none on real boxes |
| 9 | The box model | padding / border / margin sliders |
| 10 | `content-box` vs `border-box` | **two real boxes side by side against a guide line** |
| 11 | Typography | size, line-height, word-spacing, weight, line length |
| 12 | Flexbox | direction, justify, align, wrap, gap, `flex-grow` |
| 13 | Grid | equal / `1fr 2fr 1fr` / fixed+fluid / `auto-fill`, plus named areas |
| 14 | **Time to practise** | signpost → Exercise 1 |
| 15 | `position` | **flow-aware demo: siblings move, anchor parent toggle, real `fixed`, sticky** |
| 16 | transform + transition | rotate / scale / translate / skew / easing |
| 17 | animation & `@keyframes` | four animations, timing, iteration, direction |
| 18 | Responsive design | draggable container width (`@container`) |
| 19 | Custom properties & functions | one click re-themes the whole demo |
| 20 | Property reference | searchable index of 165 properties |
| 21 | Copy-paste templates | 6 ready components with live previews |
| 22 | Golden rules | — |

Two demos were rebuilt because the old ones did not actually show what they claimed:

- **`box-sizing`** now renders *two real boxes* with identical `width`, `padding` and
  `border` — one `content-box`, one `border-box` — against a dashed guide marking the
  requested width. You see the content-box one overflow the guide, with the measured
  on-screen widths printed underneath.
- **`position`** now runs inside a mock page with sibling cards, so `absolute` visibly
  removes the element from flow (the card below jumps up), a toggle adds/removes
  `position: relative` on the parent to show what the element anchors to, `fixed` uses a
  genuinely viewport-fixed element, and `sticky` sticks inside a scroll container.

## The exercises

Each exercise is a real page built in small steps. Every step gives a goal, a plain-language
"why", the exact CSS to add, and a live preview (desktop/mobile) that always matches what
the step describes. The CSS pane is editable — change it and the preview updates as you type;
"بازگرداندن کد درست" restores the correct code. Progress is remembered in `localStorage`.

| # | Exercise | Steps | Taught after | Covers |
|---|----------|-------|--------------|--------|
| 1 | **Resume website** | 12 | the Grid lesson | reset, variables, centred container, cards, flex header, typography, chips, 2-column grid, `::before` timeline, media query, re-theming |
| 2 | Profile card | 6 | the position lesson | centring, overflow, negative-margin avatar, stat row, buttons + transition |
| 3 | Responsive gallery | 6 | the Grid lesson | `auto-fill` + `minmax`, `aspect-ratio`, hover zoom, spanning item |
| 4 | Product landing page | 8 | end of course | sticky nav, hero grid, `clamp()`, CSS-only mockup, feature grid, CTA band, responsive |

The preview runs in a sandboxed `srcdoc` iframe, so exercise CSS can never leak into the app
(and vice versa) — the output you see is exactly the code in the editor.

## Features

- **Live playgrounds** — sliders, toggles and dropdowns that mutate real elements in real time.
- **Generated code view** — the CSS you just produced, syntax-highlighted, ready to copy.
- **Slide navigation** — arrow keys, `Space`, `PageUp` / `PageDown`, `Home` / `End`, plus a table-of-contents drawer.
- **Deep links** — `#7` opens lesson 7, `#ex-resume-4` opens exercise 1 at step 4.
- **Property search** — type `flex` or `shadow` to jump straight to the relevant reference entry.
- **Full RTL support** — the layout is genuinely right-to-left, not a mirrored afterthought.
- **Zero dependencies, zero third-party requests** — fonts are self-hosted, so nothing is fetched from a CDN. Works behind restrictive networks and fully offline.
- **Responsive** — works from a phone screen up to a projector.
- **Reduced motion** — every animation respects `prefers-reduced-motion`.

## Running locally

Clone and open. That is the whole procedure.

```bash
git clone https://github.com/mohammad-chavoshipor/CSSlaboratory.git
cd CSSlaboratory
open index.html          # macOS   (Linux: xdg-open, Windows: start)
```

If you prefer serving it over HTTP (recommended — the exercise previews then load the
self-hosted fonts, and deep links update the address bar):

```bash
python3 -m http.server 8080
# then visit http://localhost:8080
```

## Project structure

```
CSSlaboratory/
├── index.html      # the entire application — markup, styles and scripts
├── assets/fonts/   # self-hosted WOFF2 (149 KB total, no CDN)
├── CNAME           # custom domain for GitHub Pages
├── LICENSE         # MIT
├── README.md
└── .github/workflows/pages.yml   # publishes the site on every push to main
```

`index.html` is organised top to bottom as: `@font-face` declarations → design tokens
(`:root` custom properties) → base and component styles → per-lesson styles → exercise-UI
styles → lesson markup → exercise-UI markup → scripts.

The scripts are grouped in the same order: helpers and the CSS syntax highlighter, the slide
engine, one small IIFE per playground, the exercise data (`EX`), the exercise engine, and the
property reference plus templates. Editing a lesson means editing its `<section>` and the one
IIFE that drives it; adding an exercise means appending one object to `EX` — the UI is generated
from it.

### Fonts

Three families, self-hosted and split into Arabic and Latin subsets so a browser only
downloads what a page actually renders:

| Family | Role | Weights | Files |
|--------|------|---------|-------|
| Vazirmatn | body text (Persian + Latin) | variable, 100–900 | 79 KB |
| Lalezar | display headings | 400 | 39 KB |
| JetBrains Mono | code samples | variable, 400–800 | 31 KB |

Vazirmatn and JetBrains Mono are variable fonts, so one file per subset covers every
weight — which is also why the typography playground can slide through intermediate
weights smoothly instead of snapping between static cuts.

## Deployment

The site is published with **GitHub Pages** via the `Deploy` workflow, served at the
custom domain `css.mchavoshipor.ir`. Every push to `main` uploads the repository as-is and
republishes it — there is nothing to compile.

## Contributing

Corrections, new lessons and new exercises are welcome. Because the project is a single
file, please keep changes scoped:

1. Match the surrounding style — compact CSS, design tokens from `:root`, plain DOM APIs
   (no libraries).
2. Keep the file dependency-free. No CDN scripts, no build tooling.
3. Lessons explain one concept and stay short; multi-concept work belongs in an exercise.
4. Test in at least one Chromium browser and one Firefox before opening a pull request.

## License

[MIT](LICENSE) © Mohammad Chavoshipor
