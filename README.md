# Mauricio Cruz Brand System

Dual-surface personal brand for a Mexican AI builder based in Monterrey.

- **`meximalist.com`** — operator surface (B2B contact, press kit, advisory)
- **`mexi.wtf`** — builder hub (projects, content, community, ape mascot)

Shared design tokens, two themed expressions. **This repo represents v1 — a starting point, not a fixed direction.** See `docs/FOR_CLAUDE_DESIGN.md` for the creative ask.

---

## ▸ For Claude Design (start here)

If you're feeding this repo to Claude Design or any other generative design tool, **read `docs/FOR_CLAUDE_DESIGN.md` first.** It's a creative brief that:

- Describes who Mauricio is and what he does (rich context)
- Names hard constraints (Spanish-first, dual-surface, ape mascot stays, MTY-rooted, real photography)
- Leaves color, type, layout, and mood **wide open** for creative reinterpretation
- Asks for **3 visually distinct directions**, not 3 skins of v1

The rest of this repo (tokens, themes, palette boards, mockups) is **v1 — raw material to remix, replace, or contradict.** Don't treat it as a constraint.

---

## How to feed this to Claude Design

The form has these fields:

### 1. Link code on GitHub
```
https://github.com/mexiweb3/mexi-design-system
```

### 2. Company name and blurb
```
Mauricio Cruz Brand System: Dual-surface personal brand for a Mexican
AI builder based in Monterrey. meximalist.com (operator surface — real
headshot, B2B contact, press kit) and mexi.wtf (builder hub — 3D ape
mascot, projects, content, community). Looking for 3 distinct creative
directions, not 3 skins of v1.
```

### 3. Notes field — paste this verbatim
```
Read docs/FOR_CLAUDE_DESIGN.md in the repo first — it's the creative
brief. The rest of the repo is v1, treat it as raw material to remix
or replace, NOT as a constraint.

Hard constraints (don't break):
1. Spanish-first. English is translation.
2. Monterrey base, not CDMX.
3. Two surfaces must clearly belong to same person but feel distinct.
4. The 3D ape mascot stays as canonical mascot. Reinterpret its
   presentation, don't replace.
5. Real photography over stock/illustration.
6. Personal, not corporate, not agency.

Open creative direction (push us): color palette, typography, layout,
mood, cultural references — pick whatever serves the personality. The
current emerald + glassmorphism v1 is a starting point I already
explored. Throw it out if you want.

Show 3 distinct directions:
- Direction A: safe choice
- Direction B: risky/personal
- Direction C: surprise me

For each, give: 1-sentence thesis, hero treatment for both surfaces,
typography pick, 4-6 color palette (HEX), how the ape lives in this
world, biggest trade-off.
```

### 4. Asset uploads

Priority order (most to least important):

**Photography (the most important upload)**
- `assets/photos/headshot-bw-shirt-dots.jpg` — main editorial portrait
- `assets/photos/bridge-ape-cap-front.jpg` — ape merch (bridge image)
- `assets/photos/headshot-bw-arms-crossed.jpg` — founder pose
- `assets/photos/avatar-meximalist.jpg` — square crop avatar

**The ape mascot**
- `assets/avatar/ape.png` — canonical 3D ape

**v1 visual artifacts (for reference, not as a constraint)**
- `assets/palette/palette-board.png`
- `assets/typography/typography-specimen.png`
- `assets/components/component-sheet.png`

**Brand docs (rich context — upload these as files if the form accepts .md)**
- `docs/FOR_CLAUDE_DESIGN.md` ← the creative brief
- `docs/BRAND_BRIEF.md`
- `docs/BRAND_ARCHITECTURE.md`
- `themes/mexi-wtf/voice.md`
- `themes/meximalist/voice.md`

---

## Folder map

```
design-system/
├── README.md                       ← you are here
├── docs/
│   ├── FOR_CLAUDE_DESIGN.md        ← ★ creative brief (read first)
│   ├── BRAND_BRIEF.md              ← who, mission, audience, voice
│   ├── BRAND_ARCHITECTURE.md       ← when to use which surface
│   └── DESIGN_SYSTEM.md            ← v1 tokens, components, accessibility
├── tokens/                         ← v1 tokens (raw material)
├── themes/                         ← v1 themes + voice guides
├── components/
│   └── component-sheet.html        ← v1 live primitives
├── mockups/                        ← v1 surface mockups
├── dashboard.html                  ← v1 visual review
└── assets/
    ├── logo/                       ← v1 logo variants (replace at will)
    ├── palette/                    ← v1 palette board
    ├── typography/                 ← v1 type specimen
    ├── components/                 ← rendered v1 component sheet
    ├── og/                         ← v1 OG images (1200×630)
    ├── avatar/ape.png              ← ★ canonical ape mascot (keep)
    └── photos/                     ← ★ real photography (keep)
```

The `★` items are the ones that should survive any rebrand. Everything else is fair game.

---

## Stack (current implementation)

- HTML + Tailwind CSS (CDN, no build)
- Vercel auto-deploy from `master`
- Bilingual `/es` and `/en` routes

System is portable to plain CSS, React, Next.js, shadcn/ui.

---

## Owner

Mauricio Cruz · `m@meximalist.com` · Monterrey, MX
