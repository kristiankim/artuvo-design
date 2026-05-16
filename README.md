# Artuvo Design

A design-led website for **Artuvo Design** — a creative studio building considered, credible websites for founders and local businesses.

---

## Overview

This project contains the HTML design prototype for the Artuvo Design homepage, available in two versions:

| File | Description |
|---|---|
| `Artuvo Home.html` | **Desktop site** — vertical stacked layout (current) |
| `Artuvo Home - Mobile.html` | **Mobile prototype** — wrapped in an iOS device frame |
| `Artuvo Home v1 (split).html` | Previous desktop layout (left/right split column) |

---

## Design System

### Typography
- **Serif:** [Newsreader](https://fonts.google.com/specimen/Newsreader) — headings, lede copy, card titles, service names
- **Sans:** [Hanken Grotesk](https://fonts.google.com/specimen/Hanken+Grotesk) — UI labels, navigation, eyebrows, meta text

### Colour Tokens

```css
--charcoal: #0F0F10;   /* Primary text, dark backgrounds */
--blue-gray: #8FA1B3;  /* Italic heading accent */
--warm-gray: #D5D7DB;  /* Card placeholder backgrounds */
--taupe:     #C8B6A2;  /* CTA italic accent, card highlights */
--stone:     #F6F3EF;  /* Page background, light surfaces */

/* Ink alpha scale */
--ink-70: rgba(15, 15, 16, 0.72);
--ink-55: rgba(15, 15, 16, 0.55);
--ink-40: rgba(15, 15, 16, 0.40);
--ink-12: rgba(15, 15, 16, 0.12);
--ink-08: rgba(15, 15, 16, 0.08);
```

---

## Page Structure

### Desktop (`Artuvo Home.html`)

```
┌─────────────────────────────────────┐
│  Top bar  (logo · nav)              │
├─────────────────────────────────────┤
│  Hero                               │
│  ├── h1: "Artuvo Design."           │
│  └── Lede paragraph                 │
├─────────────────────────────────────┤
│  Work strip  (4-col animated grid)  │
├─────────────────────────────────────┤
│  Services                           │
│  ├── Left: title + description      │
│  └── Right: accordion (01–04)       │
├─────────────────────────────────────┤
│  CTA  (mailto link)                 │
├─────────────────────────────────────┤
│  Footer                             │
└─────────────────────────────────────┘
```

### Mobile (`Artuvo Home - Mobile.html`)

Rendered inside an iOS 16 device frame (402 × 874 px). Same vertical section order as desktop. Built with React + Babel (inline). Includes a **Tweaks panel** for toggling visibility of each section.

---

## Features

### Animated Work Grid
Eight abstract placeholder cards (SVG art) split across 4 columns on desktop, 2 on mobile. Alternating columns scroll up/down on a ~70s loop. Pauses on hover (desktop).

### Services Accordion
Four service tiers expand/collapse with a CSS `grid-template-rows` transition:
- **01 — Website Refresh**
- **02 — Starter Website**
- **03 — Launch Website**
- **04 — Care Plan**

### Tweaks Panel
An in-page design tool (toggle from the host toolbar) that lets you click and remove any element from the layout. Removals persist via the `TWEAK_DEFAULS.removed` array in the `<script>` block.

On mobile, the Tweaks panel exposes per-section toggle switches (show/hide top bar, heading, lede, work strip, individual services, CTA, footer) plus a "Restore all" button.

---

## Dependencies

All loaded via CDN — no build step required.

| Package | Version | Purpose |
|---|---|---|
| React | 18.3.1 | Mobile prototype UI |
| ReactDOM | 18.3.1 | Mobile prototype UI |
| Babel Standalone | 7.29.0 | Mobile prototype JSX transform |
| Google Fonts | — | Newsreader + Hanken Grotesk |

The desktop file (`Artuvo Home.html`) is plain HTML/CSS/JS with no framework dependencies.

---

## Getting Started

No build step needed. Open any `.html` file directly in a browser:

```bash
# Clone the repo
git clone https://github.com/kristiankim/artuvo-design.git
cd artuvo-design

# Open in browser
open "Artuvo Home.html"
```

Or serve locally to avoid any font CORS issues:

```bash
npx serve .
# → http://localhost:3000
```

---

## CTA Email Link

The CTA button links to a pre-filled `mailto:` for `hello@artuvo.studio`. To change the address or subject line, update the `href` on `.cta` in `Artuvo Home.html`:

```html
<a class="cta" href="mailto:hello@artuvo.studio?subject=...">
```

---

## Roadmap / Next Steps

- [ ] Replace placeholder SVG work cards with real project photography
- [ ] Add a Projects / Work index page
- [ ] Implement responsive nav (hamburger menu for mobile)
- [ ] Add page transitions / scroll-triggered reveals
- [ ] Integrate with a CMS (e.g. Sanity, Contentful) for services copy

---

## License

Design and code © MMXXVI Artuvo Design. All rights reserved.
