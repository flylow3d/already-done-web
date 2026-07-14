# It's Already Done Web Co — the business's own website

> **⚠️ Building a NEW client site? STOP and read the playbook first:**
> `C:\Users\flylo\Documents\Website Business\PLAYBOOK-building-client-sites.md`
> It contains the full pipeline (research → design → imagery → verify → ship →
> portfolio → pitch sheet), the quality bar, business rules, and every pitfall
> already hit once. Reusable tools live in `Website Business\tools\`.

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
- Domain: **alreadydoneweb.com** — purchased July 2026, registered at Porkbun,
  live as the GitHub Pages custom domain (HTTPS enforced, www works, old
  github.io URL redirects). Email: joe@ forwards to flylow3d@gmail.com via
  Porkbun forwarding + Gmail send-as; sarah@ also set up.
- Contact shown on site: joe@alreadydoneweb.com · (260) 449-1236 (real number — include on all contact references)
- Voice: confident, a little cheeky, zero agency jargon. The name is the
  pitch — every headline should sound like the work is finished because it is.
- Design: warm cream paper, Fraunces serif, sign-painter green + stamp red,
  red rubber-stamp motif done in CSS. (Original dark theme replaced July 2026.)
- Logo: green diamond with inscribed circle, corner notches, checkmark center
  (`assets/logo-diamond.png`, master). The geometry deliberately echoes the
  vintage **Greenlee Bros. trademark** — the user's family connection (see
  mrgreenlee.com). Previous round stamp logo kept as backup:
  `assets/logo-v1-circle.png`.

## Site structure

Single killer landing page, no build step, GitHub Pages:
- `index.html` — hero ("Your website? It's already done."), the 4-step
  workflow (build → show → decide → move in), Nolt's case study with device
  mockup, what's included, pricing ($399 + $99/mo), FAQ, contact CTA
- `css/style.css`
- `assets/` — Gemini-generated imagery (device mockups built from real
  screenshots of the Nolt's site via --ref)
- `print/` — business card: `business-card.html` (source of truth; edit +
  re-render via headless Chrome), `already-done-business-card-PRINT.pdf`
  (3.5×2 trim, ⅛" bleed, page 1 front / page 2 back), `preview.png`;
  `print/Payment/checkout-link-qr-code.png` — Square checkout QR
  (https://square.link/u/mhpktGnd), also copied to `..\Website Business\qr-payment.png`
  and embedded in every pitch sheet
- `Files for Nolts/` — assembled client packet (pitch + quick reference +
  agreement merged to one PDF). Sources live in `..\Website Business\`;
  re-render there and re-merge with pdf-lib to update

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
- Live: https://alreadydoneweb.com (custom domain since July 2026; the old
  https://flylow3d.github.io/already-done-web/ URL redirects to it)
- Relative links only.
