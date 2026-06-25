# Codex task: LIGHT premium redesign of the Polygon Bridge landing page (style of Polygon) + a tasteful SOURCES rail

Rebuild this static one-page site IN PLACE (your -C workdir): overwrite `index.html` + `style.css`, keep
every other file. No frameworks, no build, no external JS/libraries; tiny inline JS only. Premium and
polished -- NOT dry, NOT minimal, NOT oversized. (The current page already looks decent -- keep that bar,
make it cleaner/more premium, and add the sources rail.)

IMAGES ARE FROZEN (local): never create, overwrite, download, replace, rename, or delete any LOCAL image
(`favicon.png`, `eth.png`, `pol.png`, `og-cover.png`, any local `*.png`/`*.svg`/`*.ico`). Use ONLY the
local images already in the folder, byte-unchanged. Keep `<link rel="icon">` and the topbar brand `<img>`
on the existing `favicon.png` (no inline `<svg>` mark, no data-URI).
ONE EXCEPTION: the bottom SOURCES rail may use EXTERNAL `<img>` logos from a favicon service. No new LOCAL files.

PRESERVE from the current `index.html` (read it first): the exact keyword `Polygon Bridge` (as `<h1>` and in
`<title>`), the existing value sentence (deck `<p>` = `<meta description>`, word-for-word, light polish
only), the `<link rel=canonical>`, the money CTA target href, AND the existing topbar authority links
(Etherscan, PolygonScan, Portal) -- keep them, never drop them.

## THEME: LIGHT premium, in the style of Polygon (polygon.technology)
- Render LIGHT and premium in Polygon's spirit: a clean light base, ONE confident accent in Polygon's
  PURPLE / violet family (around `#8247E5`; derive the exact hue from `favicon.png`), soft WHITE cards with
  GENEROUS rounded corners (~16-22px), gentle soft shadows, hairline neutral borders, airy whitespace. ONE
  accent only, no rainbow. `<meta name="theme-color">` = the light base background.
- Quiet premium motion only (soft pulse on the Preview dot, gentle hover lift). Respect `prefers-reduced-motion`.

## Layout (desktop ONE screen, mobile CLEAN short scroll)
Inside `<main>`: a split hero, then the SOURCES rail (below), then the footer.
- **Topbar:** brand mark (`favicon.png`) + `Polygon Bridge` wordmark LEFT; flexible spacer; the AUTHORITY NAV
  right (Etherscan / PolygonScan / Portal, plain text, `target="_blank" rel="nofollow noopener noreferrer"`)
  -- MUST stay present and in source HTML. No topbar button.
- **Left column (basic):** `<h1>Polygon Bridge</h1>` (see H1 SIZE) -> the deck `<p>` value sentence (keyword
  in `<strong>`) -> EXACTLY THREE qualitative trust chips (e.g. `Bridge to Polygon`, `Fast & low-cost`,
  `Non-custodial`) -> ONE prominent primary CTA `Enter App`. NO `<h2>`.
- **H1 SIZE (IMPORTANT):** the hero `<h1>` must RENDER at ~80px on a 1280px desktop -- e.g.
  `font-size: clamp(2.9rem, 5.6vw, 5.1rem)`. NEVER under ~64px on desktop, NEVER a giant 120px+. Scale down on mobile.
- **Right column (the star -- a RICH bridge preview, light soft card):** light chrome + a small selector pill
  + a pulsing `Preview` pill; a From (ETH, `eth.png`) -> To (POL, `pol.png`) bridge route in two rounded
  panels with a SMALL GAP so the circular switch sits in a clean notch; the switch swaps the two; an abstract
  `Best route` micro-row (faint hop dots, NEVER fabricated numbers); a faint number-free hint; and the
  `Start Bridge` CTA. Non-interactive preview, only the switch toggles icons. No wallet connect, no fake amounts.

## BOTTOM SOURCES RAIL (MEDIUM -- a handful of authorities around the Polygon entity, tasteful)
A refined "sources" rail with a MEDIUM set (7) of authoritative sources around Polygon, each shown as its
REAL LOGO + name, linked. Use ALL of these (name | logo domain | link):
- Polygon | polygon.technology | https://polygon.technology/
- PolygonScan | polygonscan.com | https://polygonscan.com/
- L2BEAT | l2beat.com | https://l2beat.com/
- DefiLlama | defillama.com | https://defillama.com/
- CoinGecko | coingecko.com | https://www.coingecko.com/
- Etherscan | etherscan.io | https://etherscan.io/
- Chainlist | chainlist.org | https://chainlist.org/

LOGOS: load each from the Google favicon service ONLY:
`https://www.google.com/s2/favicons?sz=64&domain=<DOMAIN>` (the only external image source; create NO local
files). Each logo `<img>`: explicit `width`+`height` (e.g. 22x22), `loading="lazy"`, `alt="<name>"`, and
`onerror="this.remove()"`. DESIGN (neat + premium): a small quiet label (e.g. `Sources` / `Around the
Polygon ecosystem`), then a thin SINGLE-ROW rail of uniform source chips -- each = the logo in a small
rounded container + the name; muted/soft by default, gently colorizing + lifting on hover; even spacing,
calm, not cluttered. 7 fit one tidy row easily (no marquee needed). Each link
`target="_blank" rel="nofollow noopener noreferrer"`. Keep it THIN so desktop stays ONE screen; no horizontal overflow.

## BUTTON STYLE (2026-modern, refined -- NOT chunky)
Both CTAs: moderate size (hero ~50px tall, card ~48px, NOT 60px+), refined radius ~12-13px, font-weight
~600-650 (never heavy 800+), slight negative letter-spacing. A clean accent fill with a SUBTLE top inner
highlight (`inset 0 1px 0 rgba(255,255,255,.3)`) + a faint 1px ring; a TIGHT low accent-tinted shadow (e.g.
`0 10px 22px -12px <accent>`), NOT a big glow. A small arrow (`&rsaquo;`) that nudges ~3px right on hover
with a gentle 1px lift. Restraint + a crisp micro-interaction.

## SEO spine (LOCKED)
- `<title>` = `Polygon Bridge &mdash; <short hook>` (em-dash entity, keyword first, <=60 chars, no weak suffix).
- Exactly one `<h1>` = `Polygon Bridge`. NO `<h2>` anywhere.
- Deck `<p>` wraps `<strong>Polygon Bridge</strong>` and equals `<meta description>` word-for-word.
- Schema `@graph` = WebSite + WebApplication + Organization, truthful, no FAQ/HowTo. SEO text in source HTML.

## Claims (light, crypto-friendly)
- Confident premium copy welcome. Two floors: (1) invent NO specific numbers (stats, TVL, fees, dates,
  audits, partnerships) -- qualitative only; (2) no "guaranteed / risk-free / 100%", no fake wallet-connect.
- One small footer line: `Information on this page is for educational purposes only and is not financial advice.`

## CTAs + footer
- Exactly TWO, distinct, both -> the preserved target href, `rel="noopener noreferrer"`: hero `Enter App` +
  card `Start Bridge`. No third CTA, no topbar button.
- Footer: a `Polygon Bridge &mdash; 2026` brand line + the one educational line.

## Technical / mobile
- SEO content in SOURCE HTML; tiny INLINE `<script>` for the switch only; every LOCAL `<img>` has width+height.
- Desktop ONE screen: `body{min-height:100vh;min-height:100dvh}` + desktop media
  `{height:100vh;height:100dvh;overflow:hidden}` (vh BEFORE dvh); add a `max-height` desktop query to compress.
- MOBILE CLEAN: single column; bridge card full-width; route stacks neatly (switch rotates vertical); the
  sources rail wraps cleanly; comfortable spacing + tap targets; topbar collapses tidily (nav may hide but
  stays in source); short vertical scroll; ABSOLUTELY no horizontal overflow (`overflow-x:hidden` on html/body).
- Keep `lang="en"`; keep favicon/og/manifest/robots/sitemap referenced. Glyphs via HTML entities
  (`&mdash;`, `&rsaquo;`, `&darr;`), not literal non-ASCII.

## Self-QC
- [ ] LIGHT premium, Polygon spirit (purple accent); soft rounded cards; NOT dry.
- [ ] Topbar authority links (Etherscan / PolygonScan / Portal) present + in source HTML.
- [ ] One `<h1>` = `Polygon Bridge`; NO `<h2>`; deck `<p>` == meta description; H1 RENDERS ~80px (not under 64).
- [ ] Modern refined buttons (~50/48px, weight ~640, radius ~12px, tight shadow, arrow nudge).
- [ ] Split hero; desktop one screen no-scroll; MOBILE clean, no horizontal overflow.
- [ ] Rich number-free ETH->POL bridge preview; real eth.png/pol.png; switch in a clean notch.
- [ ] SOURCES rail: all 7 sources, real logos via Google favicon, names + nofollow links, tidy single row, no overflow, graceful onerror.
- [ ] Exactly TWO CTAs (`Enter App` + `Start Bridge`) -> target; no topbar button.
- [ ] LOCAL images byte-untouched; favicon still the icon + brand mark; footer brand line + one educational line.

Make it genuinely premium, Polygon-light, with a tasteful medium sources rail. Then stop.
