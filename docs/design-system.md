# Design System

All tokens are CSS custom properties defined in the `:root` block at the top of the `<style>` section in `src/pages/index.astro`. Always use these — never hardcode values.

## Colors

### Brand

| Token                   | Value      | Usage                         |
|------------------------|------------|-------------------------------|
| `--color-orange`        | `#C04A00`  | Primary accent, buttons, badges |
| `--color-orange-light`  | `#D96020`  | Hover state for orange elements |
| `--color-orange-pale`   | `#F5E6DC`  | Badge backgrounds, subtle tints |
| `--color-blue`          | `#5A8CA6`  | Secondary accent               |
| `--color-blue-light`    | `#7AAEC4`  | Hover state for blue elements  |
| `--color-blue-pale`     | `#DCE9F0`  | Badge backgrounds, subtle tints |
| `--color-blue-dark`     | `#3D6E87`  | Blue text variant              |

### Neutrals

| Token                   | Value                      | Usage                  |
|------------------------|----------------------------|------------------------|
| `--color-cream`         | `#FDFBF7`                  | Page background        |
| `--color-beige`         | `#EDE6DC`                  | Card backgrounds       |
| `--color-white`         | `#FFFFFF`                  | White section backgrounds |
| `--color-text`          | `#3A3632`                  | Primary body text      |
| `--color-text-light`    | `#6B6560`                  | Secondary/muted text   |
| `--color-overlay`       | `rgba(40, 30, 20, 0.65)`   | Hero image overlay     |

## Typography

**Fonts:** Playfair Display (serif, headings) + Inter (sans-serif, body). Both loaded from Google Fonts.

| Token          | Value       | px equivalent |
|---------------|-------------|---------------|
| `--text-xs`   | `0.875rem`  | 14px          |
| `--text-sm`   | `1rem`      | 16px          |
| `--text-base` | `1.125rem`  | 18px          |
| `--text-lg`   | `1.25rem`   | 20px          |
| `--text-xl`   | `1.5rem`    | 24px          |
| `--text-2xl`  | `2rem`      | 32px          |
| `--text-3xl`  | `2.5rem`    | 40px          |
| `--text-4xl`  | `3rem`      | 48px          |
| `--text-5xl`  | `4rem`      | 64px          |

## Spacing

8px grid. Use these for `margin`, `padding`, and `gap`.

| Token         | Value      | px equivalent |
|--------------|------------|---------------|
| `--space-xs`  | `0.5rem`   | 8px           |
| `--space-sm`  | `1rem`     | 16px          |
| `--space-md`  | `1.5rem`   | 24px          |
| `--space-lg`  | `2rem`     | 32px          |
| `--space-xl`  | `3rem`     | 48px          |
| `--space-2xl` | `4rem`     | 64px          |
| `--space-3xl` | `6rem`     | 96px          |

## Layout

| Token               | Value    | Usage                              |
|--------------------|----------|------------------------------------|
| `--max-width`       | `1200px` | `.container` max width             |
| `--max-width-narrow`| `860px`  | `.container-narrow` (text sections) |
| `--border-radius`   | `4px`    | All rounded corners                |

## Shadows

| Token        | Value                              |
|-------------|-----------------------------------|
| `--shadow-sm` | `0 1px 3px rgba(0,0,0,0.08)`    |
| `--shadow-md` | `0 4px 12px rgba(0,0,0,0.10)`   |
| `--shadow-lg` | `0 8px 24px rgba(0,0,0,0.12)`   |

## Transitions

| Token               | Value               |
|--------------------|---------------------|
| `--transition-fast` | `200ms ease-in-out` |
| `--transition-base` | `300ms ease-in-out` |
| `--transition-slow` | `500ms ease-in-out` |

## CSS Section Conventions

Section comments use this format:
```css
/* === SECTION NAME === */
```

Sections in order: RESET, ROOT / VARIABLES, BASE, TYPOGRAPHY, LAYOUT, NAVIGATION, HERO, STORY, DETAILS, SCHEDULE, PHOTO GALLERY, ATTIRE, GIFTS, FOOTER, RESPONSIVE, PRINT, ACCESSIBILITY.
