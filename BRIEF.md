# Banana Bytes Connect — Design Brief

A wow-factor **networking / link-in-bio page** for **Zack Ballantine**, founder of **Banana Bytes**, to hand
out at an AI conference. Four directions across two modes (2× PRO-MAX, 2× FRONTEND-FX), each anchored on Zack's
pixel-art **ServingBanana** mascot — and each showing off a *different* Higgsfield capability.

## Brand Synopsis
Banana Bytes is Zack's freelance AI web-design studio: drop a link, get a live, high-end mockup back in minutes —
AI speed, hand-finished craft. The brand voice is bold, playful, confident, anti-generic. The mascot is a pixel
banana guy holding a sunflower (the "ServingBanana" persona, also Zack's tennis handle). The page's single job:
make a conference contact go "wait, *you* built that?" and capture the connection (email, socials, save-contact).

## The four directions

### Direction: ARCADE — `direction-arcade.html`  (PRO-MAX · Motion-Driven / retro-arcade)
- **Mood**: insert-coin, neon, alive. Pure play.
- **Fonts**: Press Start 2P (display, sparing) + Space Grotesk (body).
- **Colors**: #160A24/#2A0E4F bg · #FF2E97 pink · #FFD60A banana · #22D3EE cyan · #FFF7E6 cream.
- **Signature**: a CRT arcade cabinet housing the *alive* mascot loop + a blinking PRESS START over the baked synthwave hero.
- **Higgsfield asset**: `arcade-hero.jpg` (baked pixel scene w/ real "BANANA BYTES" text) + `mascot-idle-loop` (live).

### Direction: GLASS BYTES — `direction-glass.html`  (PRO-MAX · Liquid Glass + Space Mono)
- **Mood**: premium, dev-credible, frosted, iridescent.
- **Fonts**: Space Grotesk (display) + Space Mono (data/labels).
- **Colors**: #08080C canvas · aurora #22D3EE/#FF2E97/#FFD60A · #F5F5FA text · banana accent.
- **Signature**: an iridescent glass business card that tilts toward the cursor over a living aurora, with a live status pill + local clock.
- **Higgsfield asset**: `char-render-cut.png` — the sprite reimagined as a premium 3D-plush, transparent.

### Direction: BANANA/3D — `direction-3d.html`  (FRONTEND-FX · spend boldness in one place)
- **Mood**: dark spatial gallery; quiet around one loud idea.
- **Fonts**: Bricolage Grotesque (display) + Space Mono (captions).
- **Colors**: #060507 · #FFD60A banana glow · #7C5CFF violet · #F2EEE9 off-white.
- **Signature**: the mascot as a real 3D model (generated from the 2D sprite) that spins as you scroll.
- **Higgsfield asset**: `mascot.glb` (Meshy image→3D) via `<model-viewer>`.

### Direction: LIVING SYNTH — `direction-living.html`  (FRONTEND-FX · the mascot is alive)
- **Mood**: synthwave sunset, neon, motion-forward, playful-premium.
- **Fonts**: Syne (display) + Space Mono (accents).
- **Colors**: #0B0327 indigo · #FF2E97 · #22D3EE · #FFD60A · #EDE7FF text.
- **Signature**: the live mascot glowing inside a neon portal over a parallax synthwave field.
- **Higgsfield asset**: `mascot-portal.mp4` (circular live portal) + parallax layers.

`index.html` = an arcade "SELECT MODE" selector linking all four with live previews.

## 21st.dev Component Provenance
See `21st-sources/_PROVENANCE.md`. Patterns borrowed: link-card hover-lift, glassmorphism profile card
(status pill + clock + copy-email), bento link grid, animated social-link reveals, shiny-button glow sweep.
Brand logos (Instagram, GitHub, LinkedIn, X) inlined as SVG at build.

## Content Inventory
- **Hero hook**: "I build websites in minutes." / sub: "drop me a link, get a live site back. AI speed, hand-finished craft."
- **Links (live)**: Email, Save-contact vCard, Instagram @BananaCares, GitHub Banana-Daddy, Tennis Linktree.
- **Links (placeholder, flagged)**: LinkedIn, X/Twitter, Banana Bytes site — inert "soon" pills until Zack sends URLs.

## Share Preview
- **OG image**: `images/og.jpg` (1200×630) cropped from the baked pixel arcade hero — instantly brand-recognisable.
- **OG title**: "Zack Ballantine — Banana Bytes · I build websites in minutes"
- **OG description**: "Freelance AI web design studio. Drop a link, get a live site. Let's connect."
- **Favicon**: pixel mascot (`favicon.png` 192 / `favicon-512.png`).
- **Per-page**: each direction overrides og:url/canonical to its own filename; selector carries the primary card.

## Image / Media Generation
All via **Higgsfield MCP** (forge skill) — full ledger in `IMAGE_LOG.md`. No legacy Grok/Gemini/OpenAI API used (per Zack).
Motion wired per the **higgsfield-scroll** skill (live-loop boomerang, circular portal, model-viewer scroll-spin;
transparent-video pivoted to portal after this machine's ffmpeg proved unable to emit VP9 alpha — HEVC `.mov` retained for Safari).

## Suggested Next Mockups
- A real Banana Bytes one-pager (services + the WebBlaster pipeline explained).
- Case-study gallery of past mockups (cc-tennis-club, etc.) with live links.
- A "drop your link" lead form that kicks off a build request.
- Rigged/animated 3D mascot (Meshy rigging) that waves on load.

## Production Notes
Static standalone HTML, Tailwind CDN, GitHub Pages — no build step. To productionize: move to a custom domain,
swap placeholder links for real URLs, optionally self-host the GLB/video on DreamHost (range requests) for faster
load, and add real analytics. The 21st-sources React components are cached for a Next.js rebuild if desired.
