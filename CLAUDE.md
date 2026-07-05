# It's Already Done Web Co — the business's own website

## What this is

The service website for the user's website-building business: **It's Already
Done Web Co.** — websites for northeast Indiana small businesses, built
*before* the customer pays anything. This site is both the explanation of the
service and the proof of it (it has to look killer, since it sells design).

Business model (see `..\Website Business\` for private pricing docs):
- We build the site from public info, unprompted, and show it to the owner
- $399 one-time setup when they say yes + $99/month hosting & maintenance
- Updates requested by text/email, live within 2 business days
- Month-to-month, cancel anytime, client owns domain and content
- First client/proof: Nolt's Marketplace (repo `nolts-marketplace`,
  live at https://flylow3d.github.io/nolts-marketplace/)

## Brand

- Name: **It's Already Done Web Co.** (short: Already Done)
- Domain to buy when ready: alreadydoneweb.com (itsalreadydoneweb.com also free)
- Contact shown on site: flylow3d@gmail.com (no phone yet)
- Voice: confident, a little cheeky, zero agency jargon. The name is the
  pitch — every headline should sound like the work is finished because it is.
- Design: bold & modern — near-black background, off-white type, one hot
  accent (green = done/checkmark), huge display headlines (Space Grotesk),
  "APPROVED/ALREADY DONE" rubber-stamp motif done in CSS.

## Site structure

Single killer landing page, no build step, GitHub Pages:
- `index.html` — hero ("Your website? It's already done."), the 4-step
  workflow (build → show → decide → move in), Nolt's case study with device
  mockup, what's included, pricing ($399 + $99/mo), FAQ, contact CTA
- `css/style.css`
- `assets/` — Gemini-generated imagery (device mockups built from real
  screenshots of the Nolt's site via --ref)

## Image generation

Same Node workflow as the Nolt's repo (`tools/gen_image.mjs`, key in `.env`,
gitignored — original source: fluxandthread repo):

```bash
node tools/gen_image.mjs "prompt" --out assets/x.png --ar 16:9 [--ref img.png]
```

Style anchor: dark studio scenes, soft green accent glow, photoreal devices.
Screenshots of finished client sites are the raw material — feed them as
`--ref` so mockups show REAL work, not lorem-ipsum fantasy UI.

## Deployment

- Repo: `flylow3d/already-done-web` (public) · GitHub Pages from main root
- Live: https://flylow3d.github.io/already-done-web/
- Relative links only (subpath). Custom domain alreadydoneweb.com later.
