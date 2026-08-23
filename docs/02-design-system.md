# Design system

Carried over from the positioning brief so the site and the documents look like one
practice. Implement as CSS custom properties in `src/styles/global.css`, then expose
to Tailwind through `theme.extend`.

## Palette

Neutrals are biased toward petrol, not pure grey — that bias is the point, don't
"correct" it to #888.

### Light (bare `:root`)

```css
--paper:        #F1F5F4;   /* page ground */
--surface:      #FFFFFF;   /* cards, panels */
--surface-2:    #E9EFEE;   /* table headers, insets */
--ink:          #152529;   /* primary text */
--muted:        #5B7075;   /* secondary text */
--faint:        #8A9B9E;   /* labels, eyebrows */
--rule:         #D6E0DE;   /* hairlines */
--rule-strong:  #B9C8C6;   /* emphasized borders */
--petrol:       #0C6B67;   /* primary accent */
--petrol-soft:  #D8EAE8;   /* accent wash */
--brass:        #9E6518;   /* secondary accent, numerals */
--brass-soft:   #F2E6D2;
--flag:         #9C3A3D;   /* problems, cautions, the "before" state */
--flag-soft:    #F3DEDE;
```

### Dark (`@media (prefers-color-scheme: dark)`)

```css
--paper:        #0C1517;
--surface:      #121E20;
--surface-2:    #182629;
--ink:          #E2EAE9;
--muted:        #94A8AA;
--faint:        #6C8083;
--rule:         #233335;
--rule-strong:  #33474A;
--petrol:       #4CBAB2;
--petrol-soft:  #123230;
--brass:        #D9A257;
--brass-soft:   #2E2415;
--flag:         #DE8083;
--flag-soft:    #31191A;
```

Redefine **only the token values** in the dark block. Every component references
tokens, so nothing else changes. `body` must set an explicit `background: var(--paper)`.

## Typography

Three roles, all Google Fonts:

- **Display** — `Newsreader`, weight 500, italic available. Headings, pull quotes,
  card titles. Fallback: `Georgia, "Times New Roman", serif`
- **Body** — `IBM Plex Sans`, 400/500/600. Fallback: `"Helvetica Neue", Arial, sans-serif`
- **Utility** — `IBM Plex Mono`, 400/500/600. Eyebrows, labels, prices, data.
  Fallback: `ui-monospace, Menlo, monospace`

Rules:

- Body text 17px, line-height 1.62, max width **68 characters**
- Headings get `text-wrap: balance` and negative tracking (`-0.014em` to `-0.018em`)
- Mono labels: 10.5–11.5px, uppercase, `letter-spacing: 0.13em`
- Numbers that line up in columns get `font-variant-numeric: tabular-nums`
- Hero h1: `clamp(2.5rem, 5.9vw, 4.3rem)`, line-height 1.03

Accent word inside a heading: display italic in `--petrol`. Used sparingly — once per
page at most.

## Layout

- Content max-width **1080px**, 24px side padding
- Sections separated by a 1px `--rule` hairline, ~60px vertical padding
- Section headers: a mono number chip in `--brass` on `--brass-soft`, then the h2
- Cards: `--surface` on `--paper`, 1px `--rule` border, `border-radius: 3px`.
  Small radius is deliberate — this is not a rounded-corner SaaS site
- Sibling spacing via flex/grid `gap`, never stacked margins
- Emphasized card: `--petrol` border at 1.5px, or a `--petrol-soft` fill

## Components needed for this build

- `BaseLayout` — meta, header, footer, skip link
- `Nav` — three links, no dropdowns, no hamburger animation gymnastics
- `Hero` — eyebrow, h1, standfirst, one primary CTA
- `SectionHeader` — number chip + h2 + lede
- `Card` — the generic surface panel
- `OfferCard` — price (mono, brass), title, description, what's included, CTA
- `StageStrip` — the four-stage Terrain/Load/Route/Evidence row
- `RepCard` — a labeled definition list; used once on the home page as a live sample
- `NewsletterCapture` — email input + button, sits in the footer on every page
- `Footer`

## Do not

- Add gradients, glassmorphism, or drop shadows beyond the one subtle card shadow
- Center everything — the layout is left-aligned and editorial
- Use emoji as section markers
- Add scroll animations or fade-ins. The content carries the page
