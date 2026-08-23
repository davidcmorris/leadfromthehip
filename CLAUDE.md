# Lead From The Hip — leadfromthehip.com

Marketing site for a leadership development and assessment practice. Static content
site: positioning, the method, and two paid offers. No CMS, no backend, no auth.

Owner: David Morris. Solo practitioner, ~2–4 hrs/week. Optimize every decision for
**low maintenance over cleverness** — a build step that breaks in six months is worse
than a plain one that doesn't.

## Stack

- Astro (static output, no SSR adapter)
- Tailwind CSS
- Deployed to Netlify or Vercel from GitHub `main`
- Node 20+

## Commands

```bash
npm install          # install deps
npm run dev          # local dev server, http://localhost:4321
npm run build        # production build to ./dist
npm run preview      # serve ./dist locally to verify before deploy
```

## Structure

- `src/pages/` — one `.astro` file per route. Routes: `/`, `/work-with-me`, `/about`
- `src/components/` — shared UI. Keep components dumb; no state management library
- `src/layouts/BaseLayout.astro` — shell, meta tags, header/footer
- `src/styles/global.css` — CSS custom properties (the design tokens) + Tailwind directives
- `docs/` — project context. Not shipped. Read these before writing copy or styles

## Copy

**All page copy is already written.** Do not invent marketing copy. Source it from:

- `@docs/04-copy-home.md`
- `@docs/05-copy-offers.md`
- `@docs/06-copy-about.md`

Anything in `[SQUARE BRACKETS]` is a placeholder David must fill personally —
credentials, certifications, prices, booking URL. Leave the bracket markers visible
in the built site rather than guessing a value; they are meant to be obvious.

## Design

Tokens and type scale are specified in `@docs/02-design-system.md`. Implement them as
CSS custom properties in `global.css`, then reference them from Tailwind via
`theme.extend`. Do not introduce new colors or typefaces without asking.

Light and dark themes both ship. Define the light palette on bare `:root`, redefine
only the tokens under `@media (prefers-color-scheme: dark)`. Never declare a color
solely inside a media query.

## Hard constraints — read `@docs/08-licensing-guardrails.md` before writing any copy

These will cause real legal and professional problems if violated:

1. **No publisher scale names in public copy.** Never write Hogan scale names (HPI,
   HDS, MVPI scales like "Skeptical", "Dutiful", "Bold") on this site. Public-facing
   language uses the plain-language pattern names only. This is a licensing boundary,
   not a style preference.
2. **No sample reports, no score interpretations, no percentile content.**
3. **No claim that this is therapy or treatment.** The method is behavioral coaching
   that borrows a cognitive framework. Copy must not imply clinical services.
4. **No fabricated credentials, client names, testimonials, or results.** If a section
   needs one and none exists, leave the placeholder.

## Conventions

- Semantic HTML. One `<h1>` per page. Real `<button>`/`<a>` elements, never divs.
- Mobile-first. Nothing may scroll horizontally on a 375px viewport.
- No external fonts beyond Google Fonts; no analytics or third-party scripts unless
  David asks for them by name.
- Images: `astro:assets` with explicit width/height. No layout shift.
- Accessibility is not optional: visible focus states, alt text, 4.5:1 text contrast.

## Working style

Prefer small, verifiable steps: build one page, run `npm run build`, look at it, then
move on. When a decision is genuinely ambiguous, ask rather than guessing — David has
opinions and limited time to undo things.
