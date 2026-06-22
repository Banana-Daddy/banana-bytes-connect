# BUILD BRIEF — banana-bytes-connect (shared source of truth for all 4 directions)

A **wow-factor networking / link-in-bio page** for **Zack Ballantine**, founder of **Banana Bytes**
(a freelance AI web-design studio). He's handing this URL out at an **AI conference today**. It must
make people go "wait, *you* built that?" The brand mascot is a pixel-art banana guy holding a sunflower.

Publish target: GitHub Pages at `https://banana-daddy.github.io/banana-bytes-connect/`.

---

## CONTENT (use verbatim; write brand-voice copy where a slot needs more)

- **Name:** Zack Ballantine
- **Studio:** Banana Bytes
- **Handle:** @ServingBanana
- **Hero headline (the hook):** `I build websites in minutes.`
- **Hero subhead:** `Banana Bytes — drop me a link, get a live site back. AI speed, hand-finished craft.`
- **Role / eyebrow:** `Founder · Banana Bytes` and a friendly nice-to-meet-you note (conference context): `Great to meet you — here's where to find me.`
- **Micro "what I do" (use where a direction wants a terminal/data block):**
  - `Drop a link →  live mockup in minutes`
  - `Real sites. Real images. Published live.`
  - `Web design · AI image+video · GitHub Pages → production`

### Links (build ALL of them; statuses noted)
| Label | href | status |
|---|---|---|
| Email me | `mailto:zack@zballantine.com?subject=Let%27s%20build%20something` | LIVE |
| Save my contact | (vCard download — see JS snippet below) | LIVE |
| Instagram — @BananaCares | `https://instagram.com/BananaCares` | LIVE |
| GitHub — Banana-Daddy | `https://github.com/Banana-Daddy` | LIVE |
| My tennis life — Linktree | `https://linktr.ee/ServingBanana` | LIVE |
| LinkedIn | `#` | **PLACEHOLDER** — add `data-needs-url` attr + a subtle "soon" pill |
| X / Twitter | `#` | **PLACEHOLDER** — `data-needs-url` + "soon" pill |
| Banana Bytes site | `#` | **PLACEHOLDER** — `data-needs-url` + "soon" pill |

Placeholder links: `href="#"`, add `data-needs-url="1"`, `aria-disabled="true"`, an `onclick="event.preventDefault()"`,
and a tiny muted "soon" tag so Zack never taps a dead link in front of someone. Keep them visually present.

### vCard "Save my contact" (drop this JS in every direction; wire to the Save-contact button)
```html
<script>
function saveContact(){
  const v=["BEGIN:VCARD","VERSION:3.0","N:Ballantine;Zack;;;","FN:Zack Ballantine",
  "ORG:Banana Bytes","TITLE:Founder / Web Designer","EMAIL;TYPE=INTERNET:zack@zballantine.com",
  "URL:https://instagram.com/BananaCares","NOTE:Banana Bytes — I build websites in minutes. Met at the AI conference.",
  "END:VCARD"].join("\r\n");
  const b=new Blob([v],{type:"text/vcard"});const u=URL.createObjectURL(b);
  const a=document.createElement("a");a.href=u;a.download="Zack-Ballantine.vcf";a.click();
  setTimeout(()=>URL.revokeObjectURL(u),1500);
}
</script>
```

---

## ASSET INVENTORY (all in `images/`, reference with relative paths)

| File | What it is | Best used for |
|---|---|---|
| `IMG_3035.JPG` | Original pixel-art mascot (1024², pink bg) | profile avatar everywhere |
| `arcade-hero.jpg` / `.webp` | Baked synthwave arcade scene, crisp pixel "BANANA BYTES"+"PRESS START" text, mascot, arcade cabinets, grid (1600×893) | ARCADE hero background |
| `mascot-idle-loop.mp4` / `.webm` | The mascot ALIVE — seamless boomerang loop, pink bg, bob/blink/sunflower-sway (600²) | live "arcade screen" / living portal |
| `mascot-portal.mp4` | Same loop, 480², H.264 | circular live portal (crop to circle) |
| `mascot-poster.jpg` | Sharp pixel still (600²) | video poster / reduced-motion fallback |
| `mascot-alpha.mov` | TRUE-alpha HEVC (hvc1) of the live mascot — **Safari/iOS only** | optional progressive-enhancement float |
| `mascot-alpha-poster.png` | Transparent still of the mascot | cross-browser floating decor accent |
| `char-render.png` | Premium 3D-plush mascot render, gray studio bg (1000w) | — |
| `char-render-cut.png` | Same, **transparent cutout** (944×1200) | GLASS hero figure (floats premium) |
| `mascot.glb` | Real 3D model generated from the 2D sprite (6MB, glTF 2.0) | 3D direction (model-viewer) |
| `og.jpg` | 1200×630 share card (cropped from arcade-hero) | OG meta (all pages) |
| `favicon.png` (192) / `favicon-512.png` | mascot favicon / apple-touch | meta |

**Video rules:** every `<video>` = `autoplay muted loop playsinline preload="metadata" poster="images/mascot-poster.jpg"`.
Wrap in `prefers-reduced-motion: reduce` → hide video, show poster `<img>`. iOS needs `muted`+`playsinline`.

---

## GLOBAL BUILD RULES (CLAUDE.md — every direction must follow)

- **Standalone HTML.** Tailwind via `<script src="https://cdn.tailwindcss.com"></script>`. Google Fonts via `<link>`.
  Custom CSS in a `<style>` block for keyframes/effects Tailwind can't do.
- **Mobile-first (design at 375px),** desktop is the enhancement. No horizontal scroll at any width. Test 375 / 768 / 1440.
- **Accessibility floor:** visible `:focus-visible` rings, 44px+ touch targets, `aria-label` on icon-only buttons,
  alt text on meaningful images, color-contrast ≥4.5:1 for text, `prefers-reduced-motion` respected (animations are enhancement; all content visible without them).
- **No emoji as UI icons** — use inline SVG (simple-icons paths for brand logos: Instagram, GitHub, LinkedIn, X/Twitter; Lucide-style for mail/arrow/download). `cursor-pointer` on every clickable. Hover feedback via color/opacity/shadow, not layout-shifting scale.
- **At least one real animation** (scroll reveal via IntersectionObserver — NOT animation-timeline — plus hover micro-interactions) and the direction's **signature move**.
- **Real, working links** per the table. **vCard** wired. Placeholders safely inert.
- iOS-safe: content visible by default; never gate visibility on IntersectionObserver (use it to ADD, never to hide).

### Required footer (last element on page, blend with bg color)
```html
<div style="text-align:center; padding:1.5rem 1rem; font-size:0.7rem; letter-spacing:0.05em; opacity:0.45;">
  <a href="https://instagram.com/BananaCares" target="_blank" rel="noopener" style="text-decoration:none; color:inherit;">
    Mockup created by Banana Bytes
  </a>
</div>
```

### Required share-preview meta (in `<head>`; swap PER-PAGE og:title/description/url/image + theme-color)
```html
<meta property="og:type" content="website">
<meta property="og:site_name" content="Banana Bytes">
<meta property="og:title" content="Zack Ballantine — Banana Bytes · I build websites in minutes">
<meta property="og:description" content="Freelance AI web design studio. Drop a link, get a live site. Let's connect.">
<meta property="og:url" content="https://banana-daddy.github.io/banana-bytes-connect/<THIS-FILE>">
<meta property="og:image" content="https://banana-daddy.github.io/banana-bytes-connect/images/og.jpg">
<meta property="og:image:secure_url" content="https://banana-daddy.github.io/banana-bytes-connect/images/og.jpg">
<meta property="og:image:type" content="image/jpeg">
<meta property="og:image:width" content="1200">
<meta property="og:image:height" content="630">
<meta property="og:image:alt" content="Banana Bytes — pixel-art banana mascot in a neon synthwave arcade scene">
<meta property="og:locale" content="en_US">
<meta name="twitter:card" content="summary_large_image">
<meta name="twitter:title" content="Zack Ballantine — Banana Bytes">
<meta name="twitter:description" content="I build websites in minutes. Freelance AI web design studio.">
<meta name="twitter:image" content="https://banana-daddy.github.io/banana-bytes-connect/images/og.jpg">
<meta name="twitter:image:alt" content="Banana Bytes neon arcade hero">
<meta name="theme-color" content="<DIRECTION CANVAS HEX>">
<link rel="icon" type="image/png" href="images/favicon.png">
<link rel="apple-touch-icon" sizes="512x512" href="images/favicon-512.png">
<link rel="canonical" href="https://banana-daddy.github.io/banana-bytes-connect/<THIS-FILE>">
<meta name="viewport" content="width=device-width, initial-scale=1">
```

---

## QUALITY BAR
First impression at a conference. Sweat spacing rhythm, type scale, hover states, glow consistency, mobile.
No AI-slop: no purple-on-white gradients, no centered-everything-with-no-hierarchy, no identical generic card grid,
no "Welcome to Banana Bytes." Make the signature move unmistakable. Polish like it's going to a paying client.
