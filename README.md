# Mauricio Cruz Brand System

Dual-surface personal brand for a Mexican AI builder.

- **`meximalist.com`** — professional surface (real headshot, B2B contact, press kit)
- **`mexi.wtf`** — builder hub (ape avatar, projects, content, community)

Shared design tokens, two themed expressions.

---

## Folder map

```
design-system/
├── README.md                       ← you are here
├── docs/
│   ├── BRAND_BRIEF.md              ← who, mission, audience, voice
│   ├── BRAND_ARCHITECTURE.md       ← when to use which surface
│   └── DESIGN_SYSTEM.md            ← tokens, components, accessibility
├── tokens/
│   ├── color.json                  ← color tokens
│   ├── typography.json             ← type scale + families
│   ├── spacing.json                ← spacing, radius, container, touch
│   ├── motion.json                 ← duration, easing, elevation
│   └── tokens.css                  ← all the above as CSS custom props
├── themes/
│   ├── meximalist/
│   │   ├── theme.css               ← operator surface overrides
│   │   └── voice.md                ← professional-warm voice guide
│   └── mexi-wtf/
│       ├── theme.css               ← builder surface overrides
│       └── voice.md                ← lowercase builder voice guide
├── components/
│   └── component-sheet.html        ← live primitives (cards, buttons, badges, inputs)
└── assets/
    ├── logo/
    │   ├── mark-mexi-wtf-{dark,light}.{svg,png}
    │   ├── lockup-mexi-wtf-dark.{svg,png}
    │   ├── mark-meximalist-{dark,light}.{svg,png}
    │   ├── lockup-meximalist-light.{svg,png}
    │   ├── favicon.{svg,ico}
    ├── palette/
    │   └── palette-board.{svg,png}
    ├── typography/
    │   └── typography-specimen.{svg,png}
    ├── components/
    │   └── component-sheet.png     ← rendered HTML at 1600px
    ├── og/
    │   ├── og-mexi-wtf.{svg,png}   ← 1200×630
    │   └── og-meximalist.{svg,png} ← 1200×630
    └── avatar/
        └── ape.png                 ← canon avatar for mexi.wtf
```

---

## Uploading to Claude Design

The form has 4 attachment fields. Here's what to put in each:

### 1. Link code on GitHub
```
https://github.com/mexiweb3/mexi-landing
```

### 2. Link code from your computer
Drag the entire repo folder:
```
/home/davidiego2/Documents/_active/mexi-landing
```
The uploader copies only relevant files; it won't upload heavy assets.

### 3. Upload a .fig file
Skip — no Figma source exists.

### 4. Add fonts, logos and assets
Drag these (in order of importance):

**Logos**
- `assets/logo/lockup-mexi-wtf-dark.png`
- `assets/logo/lockup-meximalist-light.png`
- `assets/logo/mark-mexi-wtf-dark.png`
- `assets/logo/mark-mexi-wtf-light.png`
- `assets/logo/mark-meximalist-dark.png`
- `assets/logo/mark-meximalist-light.png`
- `assets/logo/favicon.svg`

**Brand visuals**
- `assets/palette/palette-board.png`
- `assets/typography/typography-specimen.png`
- `assets/components/component-sheet.png`

**OG images**
- `assets/og/og-mexi-wtf.png`
- `assets/og/og-meximalist.png`

**Avatar**
- `assets/avatar/ape.png`

**Brand docs (optional but rich context)**
- `docs/BRAND_BRIEF.md`
- `docs/BRAND_ARCHITECTURE.md`
- `docs/DESIGN_SYSTEM.md`
- `themes/mexi-wtf/voice.md`
- `themes/meximalist/voice.md`

---

## What goes in the "Notes" field

See `docs/BRAND_BRIEF.md` for the full source. The condensed notes ready to paste live in the conversation that generated this folder.

---

## Stack

- HTML + Tailwind CSS (CDN, no build) — current site
- Vercel auto-deploy from `master`
- Bilingual `/es` and `/en` routes
- Tokens portable to: plain CSS, Tailwind, React, Next.js, shadcn/ui

---

## Versioning

- v1.0 · 2026-04-29
- Owner: Mauricio Cruz (`m@meximalist.com`)
