# Architecture

## Overview

Single-page static site. Astro 5 renders `src/pages/index.astro` into `dist/index.html` at build time. No server, no API, no client-side framework.

```
src/
└── pages/
    └── index.astro    ← everything: config, HTML, CSS
public/
└── images/            ← photos and Venmo QR codes (served at /images/*)
images/                ← local source images (mirrored to public/)
dist/                  ← production build output (gitignored)
```

## index.astro Structure

The file has three logical zones:

```
---
  // 1. CONFIG — variables for all wedding details + photo array
---

<!-- 2. HTML — all page sections -->

<style>
  /* 3. CSS — full design system + per-section styles */
</style>
```

## Page Sections (in DOM order)

| Section ID   | Purpose                                          |
|-------------|--------------------------------------------------|
| `#home`     | Hero: full-bleed photo, names, date, CTA         |
| `#story`    | Our Story: two-paragraph couple narrative        |
| `#details`  | Wedding Details: date, ceremony, reception cards |
| `#schedule` | Day-of timeline (ceremony → reception → last dance) |
| `#photos`   | Photo gallery grid (mapped from `photos` array)  |
| `#attire`   | Dress code + color palette swatches              |
| `#gifts`    | Two Venmo cards (Wedding Fund + Dance Fund)       |
| footer      | Names, date                                      |

Navigation links to all sections via anchor scroll. The nav has `position: sticky` with backdrop blur.

## Responsiveness

Three breakpoints via `max-width` media queries:

| Breakpoint | Target            | Key changes                              |
|------------|-------------------|------------------------------------------|
| 900px      | Tablet            | Details grid: 3-col → 1-col             |
| 768px      | Tablet/Mobile     | Nav wraps, timeline left-aligns, gallery adjusts |
| 480px      | Mobile            | Nav stacks, headings scale down, single-col gallery |

`@media (prefers-reduced-motion: reduce)` disables all animations.
`@media print` applies print-friendly styles.

## Assets

- **Photos:** 17 JPGs in `/public/images/`. Added to the `photos` array in the config section to appear in the gallery.
- **Venmo QRs:** `/public/images/venmo-wedding-qr.png` and `/public/images/venmo-honeymoon-qr.png`
- **Favicon:** `/public/favicon.svg`
- **Fonts:** Google Fonts CDN (Playfair Display + Inter), loaded in `<head>`

## No Deployment Config

There is no `wrangler.toml`, `vercel.json`, `netlify.toml`, or CI workflow. Deploy manually by running `npm run build` and uploading `dist/`.
