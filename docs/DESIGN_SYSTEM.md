# Mauricio Cruz Brand System — Design System

> One token foundation. Two themed expressions: `meximalist.com` (operator) and `mexi.wtf` (builder).

---

## 1. Architecture

```
mexi-design-system/
├── tokens/                 # Shared core (color, type, spacing, motion)
├── components/             # Primitives (button, card, badge, input, nav)
├── themes/
│   ├── meximalist/         # Operator theme (overrides + voice + photography)
│   └── mexi-wtf/           # Builder theme (overrides + voice + illustrations)
├── docs/                   # Brief, architecture, system, voice guides
└── assets/                 # Logo, palette, typography, OG, avatars
```

Tokens live in `/tokens/` as JSON + a single CSS custom-properties file. Themes consume them by setting `data-theme="meximalist"` or `data-theme="mexi-wtf"` on `<html>`.

---

## 2. Color

See `assets/palette/palette-board.png` for the visual board.

### Background
| Token | Value | Use |
|---|---|---|
| `--color-bg-primary`   | `#0a0a0a` | Base canvas (mexi-black) |
| `--color-bg-secondary` | `#111111` | Subtle elevation (mexi-dark) |
| `--color-bg-tertiary`  | `#1a1a1a` | Card surface (mexi-gray) |
| `--color-bg-inverse`   | `#f5f5f5` | Light/press mode (cream) |

### Accent
| Token | Value | Use |
|---|---|---|
| `--color-accent-primary` | `#10b981` | Emerald — CTAs, links, brand |
| `--color-accent-primary-hover` | `#34d399` | Hover state |
| `--color-accent-secondary` | `#6366f1` | Indigo — community, secondary (mexi.wtf only) |
| `--color-accent-alert` | `#f59e0b` | Amber — new, attention |
| `--color-accent-destructive` | `#ef4444` | Red — errors |

### Text
| Token | Value | Use |
|---|---|---|
| `--color-text-primary`   | `#f5f5f5` | Main text on dark |
| `--color-text-secondary` | `#9ca3af` | Body secondary |
| `--color-text-tertiary`  | `#6b7280` | Metadata |
| `--color-text-disabled`  | `#525252` | Disabled, footer |
| `--color-text-inverse`   | `#0a0a0a` | Text on light surfaces |

### Contrast guarantees
- Primary text on primary bg: **WCAG AAA** (15.9:1)
- Secondary text on primary bg: **WCAG AA** (5.7:1)
- Emerald on primary bg: **WCAG AA** (5.5:1) — large text only for body
- Black text on emerald: **WCAG AAA** (8.2:1) — preferred for emerald-bg buttons

---

## 3. Typography

See `assets/typography/typography-specimen.png`.

### Families
- **Display:** Exo 2 (400, 600, 800) — sci-fi geometric, used for headers and brand
- **Body:** Inter (400, 500, 600) — neutral, used for UI and paragraphs
- **Mono:** JetBrains Mono (or Fira Code fallback) — code, terminal moments

Both Exo 2 and Inter are free on Google Fonts.

### Scale
| Role | Family | Weight | Size | Line height |
|---|---|---|---|---|
| H1 hero | Exo 2 | 800 | 60px | 1.1 |
| H1 default | Exo 2 | 800 | 48px | 1.1 |
| H2 | Exo 2 | 800 | 36px | 1.1 |
| H3 | Exo 2 | 600 | 24px | 1.25 |
| H4 | Exo 2 | 600 | 20px | 1.25 |
| Lead | Inter | 500 | 18px | 1.5 |
| Body | Inter | 400 | 16px | 1.5 |
| Secondary | Inter | 400 | 14px | 1.5 |
| Caption | Inter | 400 | 12px | 1.5 |
| Badge | Inter | 600 | 12px | uppercase, letter-spacing 0.2em |
| Code | Mono | 400 | 14px | 1.5 |

### Theme defaults
- `meximalist`: Inter is primary; Exo 2 only on H1 (with capitalization)
- `mexi-wtf`: Exo 2 is primary on all headers (with `text-transform: lowercase`)

---

## 4. Spacing

Base unit is **0.25rem (4px)**. Everything snaps to this grid.

| Token | Value | Use |
|---|---|---|
| `--space-1` | 4px | Icon gaps |
| `--space-2` | 8px | Tight pairings |
| `--space-3` | 12px | Inline gaps |
| `--space-4` | 16px | Default spacing |
| `--space-6` | 24px | Section gaps within card |
| `--space-8` | 32px | Card padding |
| `--space-10` | 40px | Section breaks (between cards) |
| `--space-12` | 48px | Large gaps |
| `--space-16` | 64px | Hero padding |

### Containers
- Default landing page: `max-width: 42rem` (672px)
- Editorial / press: `max-width: 64rem` (1024px)

### Touch targets
Minimum **44×44px** for any interactive element. Use `--space-touch-min` (2.75rem).

---

## 5. Border radius

| Token | Value | Use |
|---|---|---|
| `--radius-sm` | 6px | Inputs |
| `--radius-md` | 8px | Buttons |
| `--radius-lg` | 12px | Small cards |
| `--radius-xl` | 16px | Default cards (primary) |
| `--radius-2xl` | 24px | Large surfaces |
| `--radius-full` | 9999px | Pills, badges, avatars |

---

## 6. Motion

### Durations
- `--duration-instant` 100ms — color hovers
- `--duration-fast` 200ms — buttons, links
- `--duration-normal` 300ms — card lifts
- `--duration-slow` 500ms — modals, page transitions

### Easing
- `--ease-out` — default for entries
- `--ease-in-out` — default for state changes
- `--ease-spring` — playful (mexi.wtf only)

### Hover patterns
- Card: `transform: translateY(-2px)` + accent border + glow shadow
- Featured card: `translateY(-3px)` + stronger glow
- Button: `translateY(-1px)` + emerald shadow halo
- Social icon: `scale(1.1)` + brand-color tint

### Reduced motion
All animations respect `prefers-reduced-motion: reduce` (see `tokens.css` global override).

---

## 7. Components

### Card
```html
<div class="card">
  <h3 class="card-title">Title</h3>
  <p class="card-description">Description</p>
</div>
```

States: default, hover, pressed, focus-visible.

Variants:
- `.card` — standard
- `.card-featured` — emerald 2px border + stronger glow
- `.card-link` — entire card is clickable (use `<a>` wrapper)

### Button
- `.btn-primary` — emerald background, black text (CTAs)
- `.btn-secondary` — transparent, emerald border, emerald text
- `.btn-ghost` — text only, hover underline

Min height: 44px. Radius: `--radius-md`.

### Badge
Small pill, uppercase 12px:
- `.badge-live` — emerald solid (LIVE, EN VIVO)
- `.badge-product` — emerald solid (PRODUCTO)
- `.badge-beta` — indigo solid (BETA)
- `.badge-new` — amber solid (NEW, 2026)
- `.badge-count` — indigo translucent (390+ eps)
- `.badge-podcast` — emerald translucent (PODCAST)

### Input
- Min height 44px
- Border `--color-border-default`, focus `--color-border-strong`
- Background `transparent` on dark, `#fff` on light

### Section header
```html
<h2 class="section-header">contenido</h2>
```
Renders as `> contenido` on `mexi-wtf` theme, plain `Contenido` (with hairline accent under) on `meximalist`.

### Avatar
- 128×128 (hero), 64×64 (header), 32×32 (inline)
- `mexi-wtf`: ape PNG, emerald translucent border, glow shadow
- `meximalist`: real headshot JPG, no border, subtle drop shadow

---

## 8. Layout patterns

### Landing page (mexi.wtf)
1. Hero (avatar + name + handle + tagline + social row)
2. Featured product (single card, emerald border)
3. Section: contenido (3 content cards)
4. Section: comunidad (2 community cards)
5. Section: conecta (2 connect cards)
6. Footer (copyright + handles + tagline)

Stack vertical, center-aligned, `max-w-2xl`.

### Landing page (meximalist.com)
1. Hero (real headshot left, name + role + lede right) — split layout
2. Brief (3 sentences, max 80 words)
3. Selected work (case studies grid, 2 cols on desktop)
4. Currently building (3 cards, less prominent)
5. Bio summary + link to /about
6. Contact (Calendly embed + email)
7. Footer

Editorial, more whitespace, `max-w-4xl`.

---

## 9. Imagery rules

| Theme | Photography | Illustration |
|---|---|---|
| `mexi-wtf` | Screenshots, code, builds, memes, behind-the-scenes | Ape avatar (canon), terminal motifs, prompt symbol |
| `meximalist` | Real photos: headshot, talks, work, behind-the-scenes (high quality only) | None (typography does the heavy lifting) |

**Never:**
- Stock illustrations
- 3D blobs / generic SaaS imagery
- The ape on `meximalist.com`
- The real headshot on `mexi.wtf`

---

## 10. Accessibility checklist

- [ ] Color contrast meets WCAG AA minimum (AAA preferred for body)
- [ ] All interactive elements have visible focus state (`:focus-visible`)
- [ ] Touch targets ≥ 44×44px
- [ ] Images have meaningful `alt` text in target language
- [ ] `prefers-reduced-motion` respected
- [ ] Heading order is sequential (no skipped levels)
- [ ] Color is never the only signal for state

---

## 11. Implementation notes

Current stack: HTML + Tailwind CSS (CDN, no build), Vercel deploy.

For new builds, the system is portable to:
- Plain HTML/CSS (use `tokens.css` directly)
- Tailwind (extend config from tokens — see existing `index.html`)
- React + CSS modules
- Next.js + shadcn/ui (compatible — emerald theme matches)

The system does not depend on a JavaScript framework.

---

## 12. Versioning

- Version: 1.0.0
- Last updated: 2026-04-29
- Owned by: Mauricio Cruz
- Tokens are stable; theme variants may evolve as new surfaces launch
