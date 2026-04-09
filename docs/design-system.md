# Design System — Astro-Volga Bank

> Single source of truth for all design tokens.
> If a value is not listed here — it cannot be used.

---

## Typography

### Font Stack

| Role | Font | Google Fonts |
|---|---|---|
| Display (headings, numbers, hero) | Unbounded | `Unbounded:wght@400;700;800;900` |
| Body (text, UI, buttons) | Golos Text | `Golos+Text:wght@400;500;600;700` |

HTML prototype import:
```html
<link href="https://fonts.googleapis.com/css2?family=Unbounded:wght@400;700;800;900&family=Golos+Text:wght@400;500;600;700&display=swap" rel="stylesheet">
```

### Type Scale

| Style | Font | Size | Weight | Line-height | Letter-spacing |
|---|---|---|---|---|---|
| Display XL (hero numbers) | Unbounded | 72px | 900 | 1.0 | -0.03em |
| Heading 1 | Unbounded | 56px | 800 | 1.14 | -0.02em |
| Heading 2 | Unbounded | 40px | 700 | 1.2 | -0.01em |
| Heading 3 | Unbounded | 28px | 700 | 1.14 | 0 |
| Heading 4 | Golos Text | 20px | 700 | 1.2 | 0 |
| Body L Bold | Golos Text | 18px | 600 | 1.33 | 0 |
| Body M | Golos Text | 16px | 400 | 1.25 | 0 |
| Body M Bold | Golos Text | 16px | 600 | 1.25 | 0 |
| Body S | Golos Text | 14px | 400 | 1.28 | 0 |
| Body S Bold | Golos Text | 14px | 600 | 1.28 | 0 |
| Caption | Golos Text | 12px | 400 | 1.33 | 0.02em |
| Caption Bold | Golos Text | 12px | 600 | 1.33 | 0.02em |

### Mobile Sizes (< 768px)

| Desktop | Mobile |
|---|---|
| Display XL 72px | 40px |
| H1 56px | 32px |
| H2 40px | 28px |
| H3 28px | 22px |

---

## Color Palette

### Core

| Token | HEX | Usage |
|---|---|---|
| Primary Blue | `#0067B1` | CTA buttons, active tabs, links. DOMINATES. |
| Primary Hover | `#005A9E` | Hover state for primary |
| Dark Navy | `#1B1F3B` | Headings, dark backgrounds, authority |
| Dark Navy Deep | `#12152B` | Bottom of dark gradient sections |
| Success Green | `#27AE60` | Conversion only: earned CTA, profit, calculator results |
| Success Hover | `#229954` | Hover state for success |
| Error Red | `#EB5757` | Errors and alerts only |

### Surfaces

| Token | Value | Usage |
|---|---|---|
| Background | `#F6F6F6` | Page background |
| Card White | `#FFFFFF` | Cards, modules |
| Border | `#E0E0E0` | Dividers, borders |
| Icon BG | `rgba(121, 129, 140, 0.12)` | Icon backgrounds |

### Text

| Token | Value |
|---|---|
| Text Primary | `#1B1F3B` |
| Text Secondary | `rgba(27, 31, 59, 0.65)` |
| Text Tertiary | `rgba(27, 31, 59, 0.4)` |
| Text On Dark | `#FFFFFF` |
| Text On Dark Muted | `rgba(255, 255, 255, 0.7)` |

### Brand Accents

| Token | HEX | Usage |
|---|---|---|
| Agent Red | `#D20000` | Agent card accent |
| Agent Green | `#2E8F57` | MIR card |

---

## Atmosphere & Depth

### Shadows

| Token | Value |
|---|---|
| Card | `0 4px 24px rgba(0, 0, 0, 0.08)` |
| Card Hover | `0 8px 32px rgba(0, 0, 0, 0.12)` |
| Card Elevated | `0 12px 48px rgba(0, 0, 0, 0.15)` |
| Button | `0 2px 8px rgba(0, 103, 177, 0.24)` |
| Glow Blue | `0 0 40px rgba(0, 103, 177, 0.2)` |
| Glow Green | `0 0 40px rgba(39, 174, 96, 0.2)` |
| Headlight | `0 0 24px rgba(255, 215, 0, 0.4)` |

### Backdrop & Overlay

| Token | Value | Usage |
|---|---|---|
| Overlay Light | `rgba(246, 246, 246, 0.85)` | Over PNG on light sections |
| Overlay Dark | `rgba(27, 31, 59, 0.75)` | Over PNG on dark sections |
| Blur Soft | `backdrop-filter: blur(20px)` | Glass effect on cards |
| Blur Strong | `backdrop-filter: blur(40px)` | Modals, overlays |
| Noise | SVG data URI, opacity 0.03-0.06 | Texture over gradients |

### Noise Texture (CSS):
```css
.noise::after {
  content: '';
  position: absolute;
  inset: 0;
  opacity: 0.04;
  background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)'/%3E%3C/svg%3E");
  pointer-events: none;
}
```

### PNG Asset Layering Pattern
```
Layer 1: PNG background (position absolute, object-fit cover, opacity 0.15-0.3)
Layer 2: CSS overlay gradient (semi-transparent, adds color tint)
Layer 3: Noise texture (::after pseudo, opacity 0.03-0.06)
Layer 4: Content (position relative, z-index above layers)
```

### Gradient Presets

| Name | Value | Where |
|---|---|---|
| Hero | `linear-gradient(165deg, #0067B1 0%, #1B1F3B 100%)` | Hero over PNG |
| Navy Section | `linear-gradient(180deg, #1B1F3B 0%, #12152B 100%)` | Trust block, dark sections |
| Card Shimmer | `linear-gradient(135deg, rgba(255,255,255,0.1) 0%, rgba(255,255,255,0) 50%)` | Highlight on dark cards |

---

## Animation Tokens

### Transition Timing

| Token | Value | When |
|---|---|---|
| Fast | 150ms ease | Hover, press, micro |
| Base | 250ms ease | Standard transitions |
| Slow | 400ms ease-out | Reveals, modals |
| Dramatic | 600ms cubic-bezier(0.16, 1, 0.3, 1) | Hero entrance, page load |
| Count-up | 800ms ease-out | Odometer number animations |

Rule: exit = 70% of enter duration.

### Signature Animation Values

| Animation | Transform | Duration | Easing | Stagger |
|---|---|---|---|---|
| Highway reveal | translateX(80px) rotate(15deg) → 0 | 500ms | cubic-bezier(0.16, 1, 0.3, 1) | — |
| Odometer count-up | number 0 → target | 800ms | ease-out | — |
| Road line | scaleX(0) → scaleX(1), transform-origin left | 300ms | ease-out | — |
| Card convoy | translateY(16px) translateX(4px) opacity(0) → 0 | 400ms | ease-out | 60ms |
| Headlight pulse | box-shadow 0 → Glow token → 0 | 400ms | ease-in-out | — |

### Conversion Moment Sequence

| Step | What | Duration | Delay |
|---|---|---|---|
| 1 | Green accent line extends (scaleX 0→1) | 200ms | 0ms (on viewport enter) |
| 2 | CTA fill: outline-gray → filled Success Green | 250ms | 150ms |
| 3 | CTA glow pulse (Glow Green shadow) | 400ms | 350ms |

### Road Line Divider (CSS)
```css
.road-line {
  height: 2px;
  background: #0067B1;
  transform: scaleX(0);
  transform-origin: left;
  transition: transform 300ms ease-out;
}
.road-line.visible {
  transform: scaleX(1);
}
```

---

## Spacing

8px grid.

| Token | Pixels |
|---|---|
| sp-2 | 2px |
| sp-4 | 4px |
| sp-8 | 8px |
| sp-12 | 12px |
| sp-16 | 16px |
| sp-24 | 24px |
| sp-32 | 32px |
| sp-40 | 40px |
| sp-48 | 48px |
| sp-64 | 64px |
| sp-80 | 80px |
| sp-120 | 120px |

---

## Border Radius

| Element | Value |
|---|---|
| Small (tags, checkboxes) | 4px |
| Medium (inputs) | 8px |
| Icons | 12px |
| Cards, buttons | 16px |
| Large sections | 24px |
| Pill (badges, avatars) | 1000px |

---

## Grid

| Parameter | Value |
|---|---|
| Max-width | 1200px |
| Columns | 12, gutter 24px |
| Container padding | 16px |
| Mobile | 390px |
| Tablet | 768px |
| Desktop | 1200px |
| Hero visual bleed | 10-15% outside container |

---

## PNG Asset Manifest

| Filename | Content | Usage |
|---|---|---|
| `gaz21-hero.png` | GAZ-21 atmospheric, 3/4 angle, motion blur | Hero section product visual |
| `gaz21-line-art.png` | Clean white line drawing on transparent | Light sections, decorative |
| `road-atmosphere.png` | Highway at dusk, bokeh lights, warm tones | Dark section backgrounds |
| `road-foggy.png` | Foggy road with depth perspective | Agents page hero |
| `river-sunset.png` | Volga river at sunset, golden light | Trust block background |
| `night-highway.png` | Night driving POV, dashboard glow | AI assistant section |
| `waves-abstract.png` | Abstract blue-green flowing waves | Section transitions, decorative |
| `card-mockup-agent.png` | Physical agent card, slight perspective tilt | Agent card section |
| `card-mockup-mir.png` | MIR card variant | Card comparison |

---

## Russian Typography Rules

Content is in Russian. Follow these rules:
- Quotes: guillemets outer, low-9 inner
- Dashes: em-dash with spaces for punctuation (not hyphens)
- Non-breaking space before short prepositions (and, in, on, with, to, etc.)
- Number formatting with spaces: 9 200, 100 000, 1 000 RUB
