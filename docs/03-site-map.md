# Site map — build 1

Three pages. That is the whole first build. Resist adding a fourth.

| Route | Purpose | Copy source |
|---|---|---|
| `/` | Establish the name, the gap, the method, and one live example of the product. Route to the offers. | `04-copy-home.md` |
| `/work-with-me` | Two offers in full, the "what I won't do" section, FAQ, booking CTA. | `05-copy-offers.md` |
| `/about` | Credibility and the personal reason the practice exists. | `06-copy-about.md` |

## Global

- **Header** — wordmark left, three links right (Home / Work with me / About). No
  dropdowns, no mega-menu, no mobile hamburger animation. At narrow widths the three
  links can simply wrap or sit in a row; they are three short words.
- **Footer** — newsletter capture, copyright, and a link to a privacy page if the
  email provider requires one.
- **Newsletter capture** — same component on every page, in the footer. The form
  action points at whichever provider David picks; leave it as a placeholder until
  he confirms.

## Deliberately not in build 1

Do not build these, even if they seem easy. They are the next build, and each one is
a reason the first build doesn't ship:

- Blog or newsletter archive
- The Load Audit interactive diagnostic
- The Interest Profiler tool
- Reps subscription or any payment flow
- A resources or reading page
- Case studies

## Definition of done

1. `npm run build` completes with no errors
2. All three pages render correctly at 375px, 768px, and 1440px
3. Nothing scrolls horizontally at 375px
4. Light and dark both legible; no color declared only inside a media query
5. Every `[PLACEHOLDER]` is either filled or visibly bracketed — none silently invented
6. Lighthouse accessibility ≥ 95
7. Deployed, and leadfromthehip.com resolves to it over HTTPS
