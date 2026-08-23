# leadfromthehip.com — start here

This folder is a **handoff kit**, not a website yet. It contains everything decided so
far: the positioning, the design tokens, the page copy, and the constraints. Claude
Code builds the actual Astro site from it.

Work through this once, top to bottom. Budget about ninety minutes for the first
sitting, most of which is waiting on installs.

---

## 1. Install Claude Code

**macOS / Linux:**
```bash
curl -fsSL https://claude.ai/install.sh | bash
```

**Windows (PowerShell):**
```powershell
irm https://claude.ai/install.ps1 | iex
```

Check it worked:
```bash
claude --version
```

Your Claude Pro or Max subscription covers Claude Code — no separate API billing.

> **One gotcha:** if you have ever set an `ANTHROPIC_API_KEY` environment variable,
> Claude Code will bill through the API instead of your subscription. Run
> `unset ANTHROPIC_API_KEY` first if you're unsure. `/status` inside a session tells
> you which one you're on.

You will also need **Node 20 or newer** — check with `node --version`, and install
from nodejs.org if it's missing or older.

---

## 2. Put this folder somewhere sensible

Move the whole `leadfromthehip` folder to wherever you keep projects — e.g.
`~/Projects/leadfromthehip`. Then:

```bash
cd ~/Projects/leadfromthehip
claude
```

First run opens a browser to log in.

---

## 3. The first session

`CLAUDE.md` is already written, so **skip `/init`** — running it would overwrite a
file that has more context in it than a code scan could produce.

Paste `first-session-prompt.md` as your opening message. It tells Claude Code exactly
what to scaffold and in what order.

Useful things to know while you're in there:

| What | How |
|---|---|
| See all commands | `/help` |
| Check billing / login | `/status` |
| Stop Claude mid-action | `Esc` |
| Undo back to an earlier point | `/rewind` |
| Start a clean context for an unrelated task | `/clear` |
| See what's eating your context window | `/context` |
| Review before committing | `/code-review` |
| Toggle how much it asks permission | `Shift+Tab` |

---

## 4. Put it on GitHub

Once the site builds locally:

```bash
git init
git add .
git commit -m "Initial site"
```

Create an empty repo on github.com, then:

```bash
git remote add origin https://github.com/YOUR-USERNAME/leadfromthehip.git
git branch -M main
git push -u origin main
```

Or just ask Claude Code to do it — it handles git conversationally.

---

## 5. Deploy

Netlify or Vercel, both free for this:

1. Sign up, choose "Import from GitHub", pick the repo
2. It auto-detects Astro — build command `npm run build`, output directory `dist`
3. Deploy. You get a live URL in a couple of minutes.
4. Point leadfromthehip.com at it in the host's domain settings, then update the
   nameservers or DNS records at your registrar. HTTPS is automatic.

Every push to `main` redeploys. That's the whole workflow from then on.

---

## What's in here

```
CLAUDE.md                      project memory — Claude Code reads this every session
first-session-prompt.md        paste this as your first message
docs/
  00-positioning.md            the wedge, the method, the voice
  02-design-system.md          palette, type, components
  03-site-map.md               three pages, and what NOT to build
  04-copy-home.md              home page copy, written
  05-copy-offers.md            offers page copy, written
  06-copy-about.md             about page — mostly placeholders for you
  08-licensing-guardrails.md   the constraints that matter most
```

---

## Before it goes live — your list, not Claude's

- [ ] Fill every `[PLACEHOLDER]` — prices, booking URL, email, credentials
- [ ] Write the About page body (only you can)
- [ ] Pick an email provider (Kit, Beehiiv, or Buttondown) and wire the form
- [ ] Set up a booking link (Cal.com or Calendly)
- [ ] Confirm your certification wording against your distributor agreement
- [ ] Decide your policy for "what if the ninety-day measure shows nothing changed"
- [ ] Read the site once on your phone

---

## One note about scope

The site is three pages. The docs deliberately list what *not* to build — the Load
Audit, the Interest Profiler tool, the blog, the subscription. All of those are good
ideas and all of them are the reason a first site doesn't ship.

Get three pages live with a booking link on them. Then add the next thing.
