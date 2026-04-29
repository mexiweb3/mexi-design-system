# Brand Architecture

How the two surfaces relate, when to use each, and how they cross-link.

---

## 1. Model

**Endorsed identity** — both surfaces are clearly "the same person" but optimized for different contexts.

```
                    Mauricio Cruz (the operator)
                              │
                ┌─────────────┴─────────────┐
                │                           │
         meximalist.com                  mexi.wtf
        (formal register)            (builder register)
                │                           │
        ┌───────┴────────┐         ┌────────┴────────┐
        │                │         │                 │
    EmpleadoDigital   Press kit  Projects        Content
    advisory          About      hub             archive
    contact           Calendar   Community       Live show
```

Both inherit from the same design system core. They differ at the **theme** layer (colors, typography defaults, photography rules) and at the **content** layer (voice, hierarchy, what's shown).

---

## 2. Job-to-be-done routing

| User intent | Send them to |
|---|---|
| "I want to hire / book Mauricio for my business" | `meximalist.com` |
| "I want to invest / partner / advise" | `meximalist.com` |
| "I'm a journalist / podcaster" | `meximalist.com/press` |
| "I saw him on X and want to see what he's building" | `mexi.wtf` |
| "I want to join the community" | `mexi.wtf` |
| "I want to find his podcast / livestream" | `mexi.wtf` |
| "I want to use a product (EmpleadoDigital, etc.)" | direct product domain (`empleadodigital.mx`) |

When in doubt: **business → meximalist, builder → mexi.wtf**.

---

## 3. Cross-linking

Both sites must acknowledge the other so users can switch register without losing context.

### From `meximalist.com` → `mexi.wtf`
- Footer: "Builder side: mexi.wtf"
- About page: "I also build in public at mexi.wtf"
- Not in primary navigation

### From `mexi.wtf` → `meximalist.com`
- Footer: "Business inquiries: meximalist.com"
- "Conecta" section: "agenda llamada profesional → meximalist.com/contact"
- Not in primary navigation

The cross-link is intentionally low-traffic. People who need the other register will find it; we don't push it.

---

## 4. Surface inventory

### `meximalist.com`

**Pages**
- `/` — Hero, brief, projects, contact
- `/about` — Long-form bio, timeline, talks
- `/press` — Press kit, headshots, bios in 3 lengths, logos
- `/contact` — Calendly + email
- `/work` — Case studies (Chapas Burgers, Casablanca, etc.)

**Tone:** Professional. Capitalized. Acentos. Spanish primary, English available.

### `mexi.wtf`

**Pages**
- `/` — Redirect by language
- `/es` — Hub: featured product → contenido → comunidad → conecta
- `/en` — Same hub, English
- `/clau` — OpenClaw meetup handout

**Subdomains** (already live)
- `bw3.mexi.wtf` — BandaWeb3 podcast site
- `vibecodeando.mexi.wtf` — livestream archive
- `call.mexi.wtf` — Calendly redirect
- `partner.mexi.wtf` — partner form
- `yo.mexi.wtf` — about page

**Tone:** Casual. lowercase. acentos opcionales. Spanish primary.

---

## 5. Domain & DNS

### Owned
- `mexi.wtf` (active, Vercel)
- `meximalist.com` (to migrate from current state)

### Recommended setup
- `meximalist.com` — primary professional surface (new)
- `mexi.wtf` — primary builder hub (current, unchanged)
- `www.meximalist.com` → `meximalist.com` (301)
- `meximalist.com/social` → `mexi.wtf` (302) — for X bio link compatibility if needed

### Email
- `m@meximalist.com` — primary professional inbox (already in use)
- `m@mexi.wtf` — alternate, alias to primary

---

## 6. Logo / mark usage

| Surface | Wordmark | Mark | Avatar |
|---|---|---|---|
| `meximalist.com` | "Mauricio Cruz" Inter SemiBold, capitalized | Monogram "MC" | Real headshot |
| `mexi.wtf` | "@meximalist" Exo 2 Bold lowercase | "M" with terminal cursor | Ape 3D |
| Cross-references | Wordmark only, never mark | — | — |

**Never mix:** the ape avatar does not appear on `meximalist.com`. The real headshot does not appear on `mexi.wtf`. Each surface owns its visual identity completely.

---

## 7. Decision tree (for new content)

```
New piece of content / page / asset
            │
            ▼
   Is it for a client / partner / press?
            │
       ┌────┴────┐
      Yes        No
       │          │
       ▼          ▼
  meximalist   Is it about a project,
               podcast, or community?
                       │
                  ┌────┴────┐
                 Yes        No
                  │          │
                  ▼          ▼
              mexi.wtf   Is it personal / behind-the-scenes?
                                   │
                              ┌────┴────┐
                             Yes        No
                              │          │
                              ▼          ▼
                          mexi.wtf  Default to mexi.wtf
                                    (builder side is the wider net)
```

---

## 8. Migration plan (meximalist.com)

Currently `meximalist.com` is not a primary surface. To activate:

1. Build `meximalist.com` from this design system using the `meximalist` theme
2. Set up DNS / Vercel project
3. Add cross-link from `mexi.wtf` footer
4. Update LinkedIn, email signature, X bio (where appropriate)
5. Press contacts updated to `m@meximalist.com` (already current)
6. Keep `mexi.wtf` 100% unchanged — it's the active hub
