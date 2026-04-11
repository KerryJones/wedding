# Content Editing Guide

All content changes are made in `src/pages/index.astro`. Run `npm run dev` to preview changes live.

## Wedding Details (config variables)

Edit the variables at the very top of `index.astro` (inside the `---` frontmatter):

```js
const weddingDate = "Saturday, June 27th, 2026";
const ceremonyTime = "3:30 PM";
const ceremonyVenue = "Morcom Gardens";
const ceremonyAddress = "700 Jean St, Oakland, CA 94610";
const receptionVenue = "The Oakland Grove";
const receptionAddress = "3630 Telegraph Ave, Oakland, CA 94609";
```

These variables are used throughout the page — changing them updates every occurrence automatically (including Google Maps links).

## Adding Photos

1. Copy the image file to `/public/images/`
2. Add the filename to the `photos` array in the frontmatter:
   ```js
   const photos = [
     "existing-photo.jpg",
     "your-new-photo.jpg",  // ← add here
   ];
   ```
Photos render in the gallery in array order.

## Our Story

Find the `<section id="story">` block (~line 88). Edit the `<p class="story-text">` paragraphs directly.

## Schedule (Day-of Timeline)

Find `<section id="schedule">`. Each event is a `<div class="timeline-item">`. To add or change an event, edit the `.timeline-time`, `.timeline-event`, and `.timeline-description` spans inside each item.

## Attire / Dress Code

Find `<section id="attire">`. Edit the text content of the description paragraphs. Color swatches are CSS-driven (`.swatch` elements with inline background colors).

## Gifts (Venmo Cards)

Find `<section id="gifts">`. Two `.venmo-card` divs:
- **Wedding Fund** — first card (orange theme)
- **Dance Fund** — second card (blue theme, `venmo-card--blue`)

To update a card: edit the `<h3>`, `<p class="venmo-desc">`, `<img>` alt text, `<p class="venmo-handle">`, and `<a>` href/text.

## Venmo QR Codes

Replace `/public/images/venmo-wedding-qr.png` or `/public/images/venmo-honeymoon-qr.png` with updated QR images. Keep the same filenames to avoid updating the HTML.
