# Astro-Volga Bank

## What This Is
Website for regional Russian bank "Astro-Volga" — honest banking for car owners and insurance agents across Russian regions. Connected to insurance company "Astro-Volga" (9.2B RUB premiums, A+(RU) rating, 250+ offices). Emotional anchor — the GAZ-21 "Volga" car.

## Tech Stack
- Prototyping: single HTML file per screen (self-contained, all CSS inline)
- Production: Next.js + React + TypeScript + Tailwind CSS
- Fonts: Unbounded (display/headings via Google Fonts) + Golos Text (body via Google Fonts)
- Animation: CSS transitions + GSAP + ScrollTrigger (CDN)
- Assets: PNG images in screens/assets/ — AI-generated atmosphere, GAZ-21 illustrations, card mockups

## Project Structure
```
astro-volga-bank/
├── CLAUDE.md
├── .claude/skills/
│   └── astro-volga-design.md
├── docs/
│   ├── design-system.md          # Tokens (single source of truth)
│   └── brand.md                  # Voice, positioning, USP
├── screens/                      # HTML prototypes (one file per screen)
│   └── assets/                   # PNG: atmosphere, GAZ-21, card mockups
│       ├── gaz21-hero.png        # GAZ-21 atmospheric, motion blur
│       ├── gaz21-line-art.png    # Clean line drawing for light sections
│       ├── road-atmosphere.png   # Highway at dusk, bokeh lights
│       ├── road-foggy.png        # Foggy road, depth perspective
│       ├── river-sunset.png      # Volga river at sunset
│       ├── night-highway.png     # Night driving, dashboard glow
│       ├── waves-abstract.png    # Abstract blue-green waves
│       ├── card-mockup-agent.png # Physical agent card, perspective
│       └── card-mockup-mir.png   # MIR card variant
└── src/                          # Next.js (production phase only)
```

## Absolute Rules
- Prototype phase: one self-contained HTML file per screen, mobile-first (390×844)
- All design tokens from docs/design-system.md — NEVER invent values
- PNG assets for atmosphere — CSS gradients only for subtle overlays, never as primary visual
- Git commit after every working result, before every experiment
- Real Russian content with real product data — never lorem ipsum
- Interaction Thesis in comment block before any screen code
- Build complex screens in phases: layout → interactions → polish. /clear between phases.
- ONE primary CTA per viewport — never 5 buttons competing for attention
- Section rhythm: never two white sections in a row, never two dark sections in a row

## Banned
- Inter, Roboto, Arial, system-ui as display font (Golos Text allowed for body only)
- Purple gradients, generic blue-to-dark gradients without texture
- Identical card grids (3 same-size cards in a row = AI slop)
- Stock photo aesthetic — only GAZ-21 illustration, icons, AI-generated atmosphere
- Centered-everything hero layouts
- Vague benefit statements like "reliable partner" or "great conditions" — use concrete numbers
- Emoji as icons
- Generic fade-in on every element — use signature animations from skill file
- Animation on everything (Alfa-Bank syndrome) — animate only what MATTERS

## Before Building Any Screen
1. Read the astro-volga-design skill
2. Read docs/design-system.md
3. Write Interaction Thesis as HTML comment
4. Phase 1: CREATIVE MODE — layout + atmosphere + PNG assets
5. Phase 2: PRECISE MODE — interactions, signature animations
6. Phase 3: PRECISE MODE — conversion moments, polish, edge cases
