# CLAUDE.md — Kerry & Angie Wedding Website

## Project Overview

Static wedding website for Kerry Jones & Angie Huang. Built with Astro 5 — single-page, no JavaScript frameworks, no backend. All content and styles live in one file: `src/pages/index.astro`.

**Live repo:** `https://github.com/KerryJones/wedding.git`

---

## Commands

```bash
npm run dev       # Dev server at http://localhost:4321 (hot reload)
npm run build     # Production build → dist/
npm run preview   # Preview production build locally
```

---

## Architecture

See [`docs/architecture.md`](docs/architecture.md) for full details.

**Key facts:**
- Everything is in `src/pages/index.astro` — HTML, CSS (~970 lines), and config variables
- No components, no layouts, no client-side JS
- All configurable data (dates, venues, photos) is declared at the **top of index.astro** in the frontmatter
- Images live in both `/images/` (source) and `/public/images/` (served)

---

## Editing Content

All wedding details are set as variables at the top of `src/pages/index.astro`:

```js
const weddingDate = "Saturday, June 27th, 2026";
const ceremonyTime = "3:30 PM";
const ceremonyVenue = "Morcom Gardens";
const ceremonyAddress = "700 Jean St, Oakland, CA 94610";
const receptionVenue = "The Oakland Grove";
const receptionAddress = "3630 Telegraph Ave, Oakland, CA 94609";
const photos = [ /* array of filenames from /public/images/ */ ];
```

To add photos: copy the file to `/public/images/` and append the filename to the `photos` array.

See [`docs/content-guide.md`](docs/content-guide.md) for section-by-section editing instructions.

---

## Design System

See [`docs/design-system.md`](docs/design-system.md) for the full token reference.

**Theme:** Burnt Orange (`#C04A00`) + Dusty Blue (`#5A8CA6`) on warm cream (`#FDFBF7`).
**Fonts:** Playfair Display (headings) + Inter (body), loaded from Google Fonts.
**Spacing/sizing:** 8px grid via CSS custom properties (`--space-*`, `--text-*`).

Never use raw hex values or pixel values in new CSS — always reference the existing CSS variables.

---

## Code Conventions

- **No new files** unless truly necessary — extend `index.astro` in place
- **CSS variables only** — no hardcoded colors, sizes, or spacing
- **Semantic HTML** — use appropriate elements; preserve existing `aria-label` and `role` attributes
- **No JavaScript** — this is a static site; avoid adding `<script>` tags
- Match the existing comment style: `/* === SECTION NAME === */` for CSS blocks, `<!-- Section Name -->` for HTML

---

## Code Review

After making code changes, always run the code-reviewer agent in a loop: spawn it, apply any suggested fixes, then spawn it again. Keep looping until it reports no more significant issues.
