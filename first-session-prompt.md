Paste everything below the line as your first message to Claude Code.

---

This folder is a handoff kit for building leadfromthehip.com. `CLAUDE.md` is already
written — please don't run `/init` or overwrite it.

Before writing any code, read these in order:

- `CLAUDE.md`
- `docs/00-positioning.md`
- `docs/02-design-system.md`
- `docs/03-site-map.md`
- `docs/08-licensing-guardrails.md`

Then work through this in stages, stopping after each one so I can look at it:

**Stage 1 — Scaffold.** Set up a new Astro project in this directory with Tailwind,
static output, no SSR adapter. Keep `CLAUDE.md`, `README.md`, `first-session-prompt.md`
and `docs/` exactly where they are. Add a sensible `.gitignore`. Confirm
`npm run dev` starts, then stop.

**Stage 2 — Design tokens.** Implement the palette and type scale from
`docs/02-design-system.md` as CSS custom properties in `src/styles/global.css`, wire
the three Google Fonts, and expose the tokens to Tailwind via `theme.extend`. Build a
temporary page that shows every token and both themes so I can check it. Stop.

**Stage 3 — Layout and components.** `BaseLayout`, `Nav`, `Footer`, and the shared
pieces listed at the end of `docs/02-design-system.md`. Real content, no lorem. Stop.

**Stage 4 — The three pages.** Home, then `/work-with-me`, then `/about`. Copy comes
verbatim from `docs/04-copy-home.md`, `docs/05-copy-offers.md`, `docs/06-copy-about.md`.

Two rules on copy, and they matter more than anything else here:

1. **Don't write new marketing copy.** It's already written. If something is missing,
   ask me rather than drafting it.
2. **Anything in `[SQUARE BRACKETS]` is a placeholder I have to fill personally** —
   prices, credentials, booking URLs. Render the brackets literally so they're
   impossible to miss. Never invent a value, especially not a credential, a
   testimonial, or a statistic.

**Stage 5 — Check it.** Run the build. Verify all three pages at 375px, 768px and
1440px, in both light and dark. Nothing should scroll sideways at 375px. Then give me
a short list of anything you had to guess at or leave unresolved.

Start with Stage 1.
