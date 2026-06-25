# Codex task: premium in-place redesign of the Anyswap landing page

You are rebuilding an EXISTING static one-page site IN PLACE. Your working directory (-C) is the
project folder. Overwrite `index.html` and `style.css`; keep every other file as-is. Deliver
production-ready, brand-true, SEO-safe output. No frameworks, no build step, no external JS libraries.

## What this page is
- Brand / exact keyword: **Anyswap** (a cross-chain token swap interface). This is a
  navigational/branded landing page that funnels visitors to an external app.
- Real assets already in this folder -- REUSE them, never invent or hand-draw replacements:
  - `favicon.png` = the REAL Anyswap brand mark (a white looping-swap glyph inside a
    blue-to-violet / indigo gradient circle). This is your color source of truth.
  - `eth.png`, `usdc.png` = real token icons for the swap widget.
  - `og-cover.png` = social cover (keep referencing it).
- Money CTA target -- keep EXACTLY, do not change: `https://avalanche-ecosystem.github.io/`
- Why we are rebuilding: the current page is too empty (one narrow centered column) and OFF-BRAND
  (it uses a mint-teal accent `#26C6A6` on cream, which is NOT Anyswap's brand).

## Primary objective
Rebuild into a restrained-premium, visually "alive" landing that fills the screen elegantly, in the
structure specified below, RE-SKINNED to Anyswap's REAL brand colors. Match the quality bar of a
custom-built product landing page -- not a template.

---

## 1. Brand colors first (the main ask)
- Anyswap's real palette = an **indigo to violet gradient** (read it from `favicon.png`). Build the
  ENTIRE theme around ONE accent in that family: an indigo / blue-violet roughly in the range
  `#5B6BF0` (blue) to `#7C3AED` (violet). Pick exact stops yourself.
- Restrained-premium discipline: ONE accent only; **neutral hairline borders** (never accent-tinted);
  soft layered shadows; at most ONE faint single-hue (indigo) vignette/glow. No rainbow, no multiple
  bright colors, no grain texture.
- Choose a **light OR dark base** -- whichever best showcases the indigo-violet brand -- and commit to
  it fully and tastefully. Make the page look unmistakably Anyswap and visually distinct (do NOT
  produce a generic dark-blue clone). Echo the favicon's gradient ONLY on small brand touches (the
  mark, optionally the primary CTA) -- keep large surfaces neutral.
- Update `<meta name="theme-color">` to match the new base.

## 2. Layout: split "command-deck" hero
Desktop = ONE screen, no scroll. Mobile = clean vertical stack with a short scroll. Inside `<main>`:
the split hero, then a thin bottom texture band, then the footer.

- **Topbar:** brand mark (`favicon.png`) + the `Anyswap` wordmark on the LEFT; a flexible spacer; the
  authority nav on the RIGHT as plain text links (keep the 3 existing references: Etherscan,
  Bridges = ethereum.org/bridges, CoinGecko; each `target="_blank" rel="nofollow noopener noreferrer"`).
  NO button in the topbar.
- **Left column (narrative / conversion):** a small eyebrow pill (e.g. a dot + `Cross-Chain Swap`)
  then `<h1>Anyswap</h1>` (big) then the deck `<p>` value sentence (keyword in `<strong>`) then one
  `<h2>` (see SEO spine) then a row of 3 short, honest, QUALITATIVE trust chips (no numbers) then ONE
  primary CTA `Enter App`.
- **Right column (the star -- a richer app preview):** an app "window" with light chrome: a
  chain/asset selector pill (a network label with a small mark) and a small pulsing `Preview` pill in
  the corner; a From -> To route using the REAL `eth.png` / `usdc.png` icons inside asset chips; a
  circular switch button that swaps From/To; a tasteful, ABSTRACT cross-chain "route" micro-row
  (e.g. a `Best route` label with a couple of faint hop dots -- brand-true, NEVER fabricated numbers);
  a faint number-free hint such as `Live quote in app`; and the `Start Swap` CTA at the bottom of the
  card. The widget is a non-interactive PREVIEW: only the switch toggles the two icons. No wallet
  connect, no fake amounts, no fake quote.

## 3. Make it feel alive (restrained) + the bottom texture band
- Add quiet, premium motion only: a soft pulse on the `Preview` dot, gentle hover lifts on CTAs and
  the switch, a subtle sheen or gradient on the brand mark or primary CTA. Nothing flashy.
- Add ONE tasteful bottom band that gives the lower area TEXTURE and life so the page does not read as
  empty. Keep it ABSTRACT and brand-true -- YOUR tasteful choice of motif (for example: a restrained
  strip of supported assets/chains, a faint repeating geometric pattern, a quiet trust line, or a
  subtle marquee). Do NOT hardcode a rigid list presented as data; keep it light, decorative,
  number-free, and RESTRAINED -- do not overdo it or clutter the screen. It exists to add texture, not
  information.

---

## SEO spine (LOCKED -- do not break)
- `<title>` front-loads the exact keyword: set it to `Anyswap` (you may optionally append a short
  intent hook as `Anyswap &mdash; <hook>`, keyword first, 60 chars max). REMOVE the current
  `- Dashboard` suffix.
- Exactly one `<h1>` and it is the exact keyword: `Anyswap`.
- The deck `<p>` is the single on-page value sentence and contains `<strong>Anyswap</strong>`; the
  `<meta name="description">` must equal that sentence word for word. Keep this crisp sentence (light
  polish allowed, keep it tight and keyword-early): "Anyswap is a cross-chain swap interface for moving
  tokens between blockchains from your own wallet."
- Add exactly one `<h2>` that contains the exact word `Anyswap` and stays on the SAME entity (no new
  topic, no drift). Example shape: `Swap across chains with Anyswap`. It must read naturally.
- Keyword present in title, H1, first sentence, and canonical (canonical stays
  `https://anyswap-v2.github.io/`). Do NOT keyword-stuff sentences.
- Schema `@graph`: keep `WebSite` + `WebApplication` + `Organization`, truthful and mirroring visible
  content. Do NOT add `FAQPage` / `HowTo` (there is no visible FAQ or step list).

## Claims and safety (LOCKED)
- Anti-fabrication is absolute: invent NO stats, TVL, volume, prices, fees, APY, user counts, audits,
  partnerships, security certifications, or dates. No real numbers are provided, so stay qualitative.
- Do NOT assert that the protocol is live, secure, audited, or that funds are safe. Keep all copy
  qualitative and navigational (what a cross-chain swap does in general). No "guaranteed / risk-free /
  100%" language anywhere.
- Exactly ONE educational disclaimer, only in the footer:
  `Information on this page is for educational purposes only and is not financial advice.`
- No hidden text, no fake wallet-connect / deposit / transaction flow.

## CTAs (exactly TWO, distinct names)
Both link to `https://avalanche-ecosystem.github.io/` with `rel="noopener noreferrer"` (dofollow):
- Left hero primary button: `Enter App`
- App-card primary button: `Start Swap`
No third CTA, no topbar button, no two buttons sharing a label.

## Technical / performance
- All SEO-critical content lives in the SOURCE HTML (must be present with JS disabled). Use only a tiny
  INLINE `<script>` for the switch (swap the innerHTML of the two asset chips). No external app.js, no
  libraries, no blocking third-party scripts.
- Every `<img>` has explicit `width` and `height` (anti-CLS). One stylesheet (`style.css`).
- Desktop one-screen: set body to `min-height: 100vh; min-height: 100dvh;` and, in the desktop media
  query, `height: 100vh; height: 100dvh; overflow: hidden;` (the `vh` line BEFORE the `dvh` line as a
  fallback -- required). Mobile (around 700-920px and below): collapse the split to one column, hide
  the nav, allow a short vertical scroll, and guarantee NO horizontal overflow.
- Keep `lang="en"`. Keep `favicon.png`, `og-cover.png`, `site.webmanifest`, `robots.txt`,
  `sitemap.xml` working and referenced.
- For glyphs use HTML entities (e.g. `&mdash;`, `&rsaquo;`, `&darr;`, `&rarr;`), NOT literal non-ASCII
  characters.

## Self-QC before finishing (every box must pass)
- [ ] Theme rebuilt around the indigo/violet brand accent (ONE accent), neutral hairlines, restrained;
      brand-true to the favicon; not mint-teal; not a generic clone.
- [ ] `<title>` front-loads `Anyswap` (no `- Dashboard`); exactly one `<h1>` = `Anyswap`; one `<h2>`
      contains `Anyswap`, same entity, reads naturally.
- [ ] Deck `<p>` equals the meta description and wraps `<strong>Anyswap</strong>`.
- [ ] Split hero: left text / right rich preview; desktop one screen with no scroll; mobile stacks with
      a short scroll and no horizontal overflow.
- [ ] Rich preview: From/To route with real eth/usdc icons, working switch, `Preview` pill, abstract
      cross-chain route row, all number-free; no fake quote/amount.
- [ ] Exactly TWO CTAs: hero `Enter App` + card `Start Swap`, both to the target; distinct names; no
      topbar button.
- [ ] One restrained, abstract, brand-true bottom texture band; adds life without clutter; number-free.
- [ ] No fabricated stats/security/liveness claims; exactly one educational disclaimer in the footer.
- [ ] Schema = WebSite + WebApplication + Organization, truthful, no FAQ/HowTo; content in source HTML;
      only tiny inline JS.
- [ ] All `<img>` have width and height; favicon/og/manifest/robots/sitemap intact.

Make the result genuinely premium and brand-true. Then stop.
