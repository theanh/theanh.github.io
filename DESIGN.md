# Design System — theanh.github.io

Editorial portfolio. The aesthetic register is quality print journalism: warm paper, serif body, neutral sans headlines, monospace labels. Every typographic choice is intentional.

---

## Typography

Three-layer system. Each layer has a distinct job.

| Layer | Stack | Use |
|-------|-------|-----|
| Display | `--font-display`: system-ui / SF Pro / Segoe UI | Headings (h1–h4), nav, stats, card titles |
| Body | `--font-body`: Spectral → Georgia fallback | All running prose |
| Mono | `--font-mono`: JetBrains Mono → ui-monospace | Kickers, labels, captions, metadata, code |

**Why system-ui for display?** Newspapers pair a neutral grotesque sans against a warm text serif — Helvetica headlines, Times body. System-ui gives SF Pro on macOS and Segoe UI on Windows: both are high-quality grotesque sans typefaces that render beautifully at every weight and size, carry no visual baggage, and cost zero bytes. The warmth comes from Spectral and the parchment palette; the display font stays out of the way.

**Why Spectral?** A contemporary text serif with strong italics and good weight range. Reads like a quality magazine at 19px body size. Falls back to Georgia, which maintains the editorial register on systems without the Google Fonts load.

**Why JetBrains Mono?** Distinctive monospace for labels and kickers — reinforces the "technical precision" signal alongside the editorial serif. Pairs well with both layers.

---

## Color

Warm neutral palette. No cool grays, no blue-tinted whites.

| Token | Hex | Use |
|-------|-----|-----|
| `--bg` | `#f7f4ee` | Page background — warm parchment |
| `--paper` / `--surface` | `#fbfaf6` / `#faf8f3` | Card surfaces, slightly lighter than bg |
| `--text` | `#1c1a14` | Body copy — near-black with warm undertone |
| `--muted` | `#6b6256` | Captions, labels, metadata — 4.8:1 on bg, passes WCAG AA |
| `--soft` | `#4a4438` | Mid-weight secondary text (case study pages) |
| `--yellow` | `#ffd139` | Accent — numbered lists, drop-cap highlight, active state |
| `--theme` | `rgba(255,209,57,0.5)` | Yellow at half opacity — borders, shadows |
| `--blue` | `#2563eb` | Links only |
| `--green` | `#16a34a` | Positive metrics, success states |
| `--amber` | `#d97706` | Warnings, neutral signals |

Rule: the warm neutrals (bg, paper, text, muted) form the base. Yellow is the only chromatic accent. Blue, green, and amber are semantic — used only where they carry meaning, never decoratively.

---

## Spacing

8px base grid. Section padding at multiples of 8. Card padding at 18–28px. Max content width 860px (portfolio) / 720px (case studies).

---

## Components

### Masthead (case study pages)
Sticky header with brand link (left) and page action link (right). `padding: 13px 4px` on all anchor children ensures ≥44px touch target.

### Nav (portfolio)
Sticky top nav. Links at `padding: 12px 4px` for ≥44px touch target on desktop. Responsive overrides at 720px and 480px increase to `14px` vertical.

### Section label (`p.section-label`)
Used as navigational wayfinder between sections — monospace, 0.72rem, uppercase, muted. Visually smaller than `h3` card titles by design: the label names the zone, the h3 names the item. Intentionally a `<p>`, not a heading — keeps the heading tree clean (h1 → h3) and avoids confusing screen reader users with a heading that appears visually subordinate to the elements beneath it.

### Stats row
`--font-display` for the number, `--font-mono` at 0.72rem for the label. Numbers use `font-variant-numeric: tabular-nums`.

### Brushstroke rule
Inline SVG with feTurbulence displacement — gives a hand-drawn ink feel. Used as section dividers and on the drop-cap background. Not a PNG, not a third-party asset.

---

## What this is not

- No purple/violet gradients
- No 3-column feature grids with icons in colored circles
- No decorative blobs or wavy SVG dividers
- No centered hero copy ("Welcome to...", "Unlock the power of...")
- No emoji as design elements

The site is editorial, not SaaS. Every section has one job. If a section feels empty, it needs better content — not decoration.
