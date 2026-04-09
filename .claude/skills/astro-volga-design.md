---
name: astro-volga-design
description: Design intelligence for Astro-Volga Bank website. Use when building any screen or component. Provides aesthetic direction, signature animations, hero architecture, section rhythm, conversion patterns, and quality gates. Prototype phase = single HTML files with PNG assets.
---

This skill creates screens for Astro-Volga Bank that feel like a confident, modern regional bank — not a template, not a fintech startup, not Sber. The litmus test: "Would a 45-year-old insurance agent from Samara understand this in 5 seconds AND would a designer screenshot this?"

Read `docs/design-system.md` before building ANY screen. Tokens live there. This skill provides taste and choreography — not values.

## Interaction Thesis (mandatory)

Before writing any code, write one sentence as an HTML comment:
"The user is [emotional state]. They arrive from [context]. They want [action]. The unforgettable micro-moment is [specific instant]."

### Examples by screen temperature:
- **Hero:** "User landed from Google ads. Skeptical — another bank? The 11% number must HIT before doubt kicks in. Micro-moment: the odometer counting from 0% to 11% in 800ms."
- **Agent page:** "Insurance agent, 42, Samara. She's heard 'passive income' before. She wants PROOF. Micro-moment: real calculation appearing — 'With 50 clients: 50,000 RUB/month' — her specific scenario."
- **Card comparison:** "Car owner comparing cards. He'll bounce in 8 seconds if no clear benefit. Micro-moment: the cashback number 1.5% appears NEXT TO his typical gas station spend."
- **Trust block:** "User is almost convinced but needs reassurance. Micro-moment: the 9.2B number counting up while A+(RU) badge fades in — authority earned through data."

## Aesthetic Direction

### We ARE:
- Tochka Bank — clean navigation, structured info, respects user's time
- Revolut — bold typography, numbers that sell, confident product pages with choreographed scroll
- A Soviet automotive museum — the GAZ-21 is emotional heritage, not decoration
- A well-lit regional office — trustworthy, warm, practical, not trying to be Moscow

### We Are NOT:
- Sber/Alfa visual noise (too many CTAs, overwhelming animation, desperate energy)
- Generic bank template (stock photos, blue gradient hero, "Reliable partner" tagline)
- Fintech startup (dark theme, crypto aesthetic, English buzzwords on Russian site)
- T-Bank storytelling (too playful for our 30-55 audience)
- Any AI-generated site with Inter font and identical card grids

### Why Competitors Fail (context for Claude Code):
- **Sber:** 5+ CTAs visible simultaneously. Eye has nowhere to rest. We show ONE primary CTA per viewport.
- **Alfa:** Animation on everything = animation on nothing. We animate only what MATTERS.
- **T-Bank:** Storytelling tone works for 25yo Moscow. Our 45yo Samara agent needs NUMBERS not stories.
- **Generic templates:** Hero says "Reliable partner since 2005." Ours says "11%" — the number IS the headline.

### The Formula:
Clean white space + Primary Blue anchors trust + Success Green at conversion moments only + GAZ-21 as brand signature + concrete numbers everywhere + PNG atmospheric assets for depth + signature animations for identity.

## Hero Architecture

Hero = asymmetric split. Left 55%: headline (Unbounded 800) + one metric in Display XL + CTA stack. Right 45%: product visual (card mockup, GAZ-21, or phone) BLEEDING outside container by 10-15%. The product visual overlaps the section boundary — it is NOT contained.

Background layering: PNG asset at 15-25% opacity + gradient overlay from design-system.md + noise texture. One large number (11%, 9.2B, 1,000 RUB) in Display XL — this number is the HOOK that stops scrolling.

Mobile: stack vertically, visual scales down but KEEPS the bleed. Number stays Display XL even on mobile (40px minimum).

## Signature Animations

These are Astro-Volga's movement vocabulary. Use THESE — not generic fade-in.

- **Highway reveal:** content slides in from right at 15° angle, like a car passing. Use for hero sections and major content entrances.
- **Odometer count-up:** numbers animate from 0 to target value with easeOut. 800ms duration. Use for ALL key metrics (11%, 9.2B, 250+, 1,000 RUB).
- **Road line:** thin horizontal accent line (2px, primary blue) extends left→right before content appears. 300ms. Use as section dividers between major blocks.
- **Card convoy:** cards enter staggered with 60ms delay, each offset vertically by 4px then settling to 0. Like cars in a convoy. Use for all card grids.
- **Headlight pulse:** subtle glow animation on primary visual elements. Single pulse, not infinite. Use on GAZ-21 headlights and hero product shots.

Exit animations = 70% of enter duration. Always.

## Conversion Moment Pattern

Green CTA does not just SIT there. The user EARNS the green button by reading the value proposition:

1. Green CTA starts as outline/muted state (gray border, no fill)
2. When scroll brings it into viewport: thin green line extends under the benefit list (200ms)
3. Button transitions from outline-gray to filled-green with glow (250ms)
4. Subtle green glow pulse once (400ms) — attention without aggression
5. After first trigger, button stays green (no re-animation on re-scroll)

This pattern applies to: "Become an agent" button, calculator result CTA, agent card CTA.

## Section Rhythm (scroll narrative)

The page BREATHES. Alternate these patterns — never two of the same type in a row:

1. **DARK full-bleed** (navy + PNG atmosphere) — emotional, authority. Used for: hero, trust block, AI assistant showcase.
2. **WHITE contained** (max-width 1200px, #F6F6F6 or #FFFFFF) — data, features, cards. Used for: tariffs, deposits, how-it-works.
3. **ACCENT moment** — one metric in Display XL, one CTA, generous breathing space. Minimal content. Used for: transition between major sections, key stat callout.
4. **SOCIAL PROOF strip** — agent testimonials, company numbers, credentials. Can be dark or light. Used for: trust building between product sections.

Rule: if you just built a white section, the next MUST be dark or accent. The scroll journey has rhythm like music — verse, chorus, bridge.

## Design Dimensions

### Typography
Unbounded for display: headings, hero numbers, key metrics. Creates instant character.
Golos Text for body: clean, Russian-designed, excellent Cyrillic.
Tension through SCALE: H1 56px/800 next to body 14px/400. Big numbers sell: "11%" in Display XL.
Russian typography: guillemets, em-dashes, non-breaking spaces before short prepositions.

### Color Hierarchy
Blue DOMINATES the page (CTAs, links, focus states). Green appears ONLY at conversion moments with the Conversion Moment Pattern above. Navy for authority (dark sections, headings). Never distribute colors evenly — blue leads, green punctuates.

### Motion Timing
- Hover/press: 150ms ease
- Standard: 250ms ease
- Reveals: 400ms ease-out, stagger 40-60ms per element
- Hero entrance: 600ms orchestrated sequence
- Odometer count-up: 800ms ease-out
- Exit = 70% of enter duration
- prefers-reduced-motion: mandatory — static fallback, no animations

### Spatial Composition
Asymmetry over symmetry. Featured card 1.5x width of others. 60% negative space is trust. Hero: split layout with product visual bleeding outside container. Break the grid deliberately.

### Atmosphere (critical)
PNG assets from /assets for backgrounds — NOT CSS gradients as primary visual. Every section has atmosphere — no flat solid backgrounds. Layer: PNG base (opacity 0.15-0.3) + CSS overlay gradient + noise texture + content.

## Anti-Patterns (NEVER)
- All cards same size, same padding, same shadow → BREAK symmetry
- Heading + paragraph + button repeated identically → VARY rhythm
- Blue used equally everywhere → Blue = PRIMARY CTAs only
- Every element fades in identically → USE signature animations above
- Generic hero: big text centered, subtitle centered, button centered → USE hero architecture above
- Vague benefits → REPLACE with concrete numbers
- CSS-only backgrounds → USE PNG assets for depth
- Cheap SVG icons in circles → quality icons or no icons
- Two same-type sections in a row → FOLLOW section rhythm
- Green button just sitting there → USE conversion moment pattern

## Quality Gates
Before delivering any screen:
- [ ] Interaction Thesis written in comment block
- [ ] All tokens from design-system.md — zero invented values
- [ ] Fonts: Unbounded for display, Golos Text for body — nothing else
- [ ] One concrete number visible per section minimum
- [ ] Background has atmosphere (PNG asset, texture, gradient overlay) — not flat solid
- [ ] Featured element breaks the pattern (larger card, different rhythm, asymmetric placement)
- [ ] Signature animations used — no generic fade-in
- [ ] Section rhythm respected — no two same-type sections adjacent
- [ ] Conversion CTAs use the conversion moment pattern (earned green)
- [ ] ONE primary CTA per viewport
- [ ] Hero uses asymmetric split with bleeding product visual
- [ ] Works at 390px mobile without horizontal scroll
- [ ] prefers-reduced-motion respected
- [ ] Screenshot test: would I send this to a designer friend?

## Reference Loading
| Building... | Load |
|---|---|
| Any screen | `docs/design-system.md` (always) |
| Need voice/tone | `docs/brand.md` |
