# 21st.dev Component Provenance — banana-bytes-connect

Inspiration pass run 2026-06-22 (DIRECTION). Free `21st_magic_component_inspiration` searches.
Translated to vanilla HTML + Tailwind CDN (React/Tailwind scaffolding stripped, visual logic kept).

| Query | Component | Borrowed | Used in |
|---|---|---|---|
| `link in bio` | LinkCard (card-26) | hover lift (`-translate-y` + spring), illustration anchored bottom-right of tile, serif title | link tiles (all directions) |
| `glassmorphism profile card` | Glassmorphism Profile Card (Berat) | live status pill (pulsing dot) + local clock, Copy-Email button, lime glow drop-shadow under card | GLASS BYTES (Pro-Max v2) |
| `glassmorphism profile card` | Glass Card (molecule) | `backdrop-blur-md` + `bg-*/30` border tokens | GLASS BYTES |
| `bento grid links` | Bento Grid (colSpan + persistent hover, radial-dot hover wash) | mixed-span tile grid, hover reveal CTA arrow | link grid (Pro-Max v1, FX) |
| `animated social buttons` | AnimatedSocialLinks | icon floats up + blur-in on hover, siblings dim to 50% | social row (FX v2 LIVING SYNTH) |
| `animated social buttons` | Shiny Button | gradient sheen sweep on hover, glow shadow per-variant | social icon buttons (all) |

Notes: all components are React/shadcn; we keep only the Tailwind classes + interaction timing.
Logos pulled via `logo_search` at BUILD time (GitHub, Instagram, LinkedIn, X) — SVG, dropped inline.
