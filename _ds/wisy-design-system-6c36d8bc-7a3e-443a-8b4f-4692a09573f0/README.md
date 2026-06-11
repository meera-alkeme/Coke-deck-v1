# Wisy Design System

> The intelligence layer for CPG retail execution — one system that sees the shelf, ranks what matters, and tells field teams what to do before they leave the store.

Wisy is an AI-native platform for CPG (consumer packaged goods) brands, agencies, and grocery retailers. Field reps photograph shelves with a phone or tablet; the platform runs computer-vision recognition (with offline in-app AI) to detect out-of-stocks, share-of-shelf, planogram compliance, competitor presence, and promotion execution — then surfaces revenue-ranked actions to the rep in seconds and aggregated compliance to HQ in near real time.

The name combines **wise + easy**. The brand voice and visual identity reflect that: confident and direct, with a soft-edged friendliness that comes from generous radii, a lime-on-indigo accent pair, and a wordmark that ends in `:` — like a thought just before it tells you what to do.

---

## Sources used to build this system

| Source | Status | Notes |
|---|---|---|
| `uploads/drive-download-20260519T161306Z-3-001.zip` | ✅ Used | Contained 5 brand files: `Wisy_Logo_Indigo.png`, `Wisy_Logo_Indigo_Transparent.png`, `Wisy_Logo_White.png`, `Wordmark_Indigo_Transparent.png`, `Brand_Style Tile.png` (the canonical foundations reference). Extracted to `assets/`. |
| https://wisy.ai/en/ | ⚠️ Marketing copy only | Site is client-side rendered, so only meta-tags and SEO copy were reachable through fetch. Hero pitch in the meta description: "real-time shelf intelligence, prioritized actions, and revenue-ranked insights in every store." |
| Public coverage of Wisy (Cloud Wars, LinkedIn, Vision Group Retail) | ✅ Used for product model | Background on workflow, offline AI, customer stories (e.g. CCU in Chile). |
| Codebase | ❌ Not provided | No production code or Figma file was attached. UI kits in this system are recreations from the brand foundations + the public product model, NOT from source. **If you have a Figma or repo, attach it and ask me to re-do the kits with real components.** |

---

## Index of this system

```
README.md                 ← you are here
SKILL.md                  ← skill manifest for using this in Claude Code
colors_and_type.css       ← all CSS variables + semantic type classes
assets/                   ← logos, wordmarks, brand style tile
fonts/                    ← (Google Fonts — loaded via @import in colors_and_type.css)
preview/                  ← design-system cards rendered in the Design System tab
ui_kits/
  mobile_app/             ← Field rep app (phone): capture, scan results, action list
  web_dashboard/          ← HQ dashboard (desktop): compliance, alerts, store grid
  marketing_site/         ← wisy.ai landing-page kit
slides/                   ← (not built — no slide template was provided)
```

---

## Content fundamentals

How Wisy writes.

**Voice.** Confident, plain, action-leaning. Wisy never sounds like a research vendor; it sounds like the smartest person on your field team who happens to have already done the math. The pitch is always *"here's what to do,"* never *"here's a dashboard for you to interpret."*

**Casing.** Sentence case for everything that's prose: headlines, buttons, nav items, body. UPPERCASE is reserved for mono labels — kickers, section tags, status pills, ALL-CAPS captions in the lower hierarchy. Title Case is not used.

**Person.** Wisy speaks to **you** (the rep, the regional manager, the brand) and refers to itself in the third person ("Wisy ranks what matters"). The first-person "we" appears on the marketing site when talking about company stance.

**Sentence shape.** Short, declarative, often three-beat rhythm — *"See your shelf. Rank what matters. Act before you leave."* Em-dashes are common for setup-payoff phrasing (*"the intelligence layer — for retail execution"*). Hyphens are used inline ("revenue-ranked", "AI-native"). Numbers are concrete and unhedged: "30+ minutes → seconds", "25% efficiency boost", "250 SKUs."

**Vocabulary.** *Shelf, store, rep, field team, SKU, share of shelf, out-of-stock, planogram, execution, intelligence, revenue-ranked, prioritized actions, on-shelf availability.* Avoid "leverage," "synergy," "solution," "robust." Prefer "see," "rank," "tell," "act."

**Emoji & symbols.** No emoji. The colon `:` from the wordmark is the closest thing Wisy has to an iconographic flourish, and it's earned — it appears only in the lockup, never decoratively in copy.

**Examples lifted from real Wisy surfaces.**
- *"An AI-native platform designing the intelligence layer for retail execution."* (brand style tile)
- *"We're rethinking retail execution from the ground up — for the age of AI."* (brand style tile)
- *"Wisy is an AI platform for CPG field teams — real-time shelf intelligence, prioritized actions, and revenue-ranked insights in every store."* (site meta)

**Example transformations.**
| Don't | Do |
|---|---|
| "Leverage AI to optimize your retail KPIs." | "See your shelf. Act before you leave the store." |
| "Our robust solution offers comprehensive insights." | "Photograph the shelf. Wisy ranks the fix list by revenue." |
| "Robust enterprise-grade computer vision pipeline." | "Image recognition in milliseconds. Even offline." |

---

## Visual foundations

**Palette.** Two-color brand, with neutrals and lavender supporting tints:
- **Indigo `#5354ED`** — the primary signature color. Used for the wordmark, primary CTAs, accent type, links, and large *brand moment* fills. It's a saturated, slightly cool true-blue that reads pure blue at scale — never veers into purple.
- **Lime `#DDF45B`** — the bright accent. Used as a counterweight to indigo: highlight pills, key data callouts, hover states on dark surfaces, a tone-shift block on a long page. Always paired with black text, never indigo text.
- **Lavender tints `#CDD1FF` / `#F0F1FF`** — soft surfaces that telegraph "Wisy-ness" without using saturated indigo. The `F0F1FF` wash is the most-used surface tint and shows up under text blocks and tag pills.
- **Neutrals `#000`, `#AAA`, `#F5F5F5`, `#FFF`** — text and surfaces. Black is used liberally for body text; mid-gray for placeholders/captions. `#F5F5F5` is the standard *content surface* card color.

Wisy's color rule of thumb: **one bold color per view.** If indigo is loud (full bleed or CTA), lime stays small (a pill, a single highlight). If lime is loud (an accent block), indigo stays small.

**Type.** *Figtree* (Google Fonts) for everything humans read — Regular, Medium, SemiBold. *Roboto Mono* (Google Fonts) for tags, captions, status labels, and the "kicker" line above a headline — always uppercase, always letter-spaced. Display sizes use Figtree Medium (not Bold) — Wisy display type is large, tight-tracked, but never heavy.

**Backgrounds.** Mostly clean white or `#F5F5F5`. Lavender wash `#F0F1FF` is the "soft callout" background. Full-bleed indigo is reserved for hero moments and section breaks. No gradients, no patterns, no textures, no hand-drawn illustration. Photography of real shelves and real stores is the imagery vocabulary — bright, daylight-balanced, true color, no grain or filter. Product photos are tight crops on white.

**Animation.** Snappy and confident. Default easing is `cubic-bezier(0.16, 1, 0.30, 1)` (a soft-out curve that feels like a snap). Durations: 120ms for hover state changes, 200ms for component transitions, 360ms for page-level reveals. No bounces, no spring physics with overshoot, no lingering fades. Things move and arrive; they don't perform.

**Hover.** Buttons darken one step (indigo → `#3F3FD5`); text links draw a 1px underline in indigo from transparent. Cards lift one shadow step (`shadow-sm` → `shadow-md`) and the border picks up `--border-2` (lavender). Icon buttons get an `#F0F1FF` background fill.

**Press.** One more step darker (indigo → `#2B2BB8`); buttons scale to `0.98` for 90ms then return. No drop-shadow change on press.

**Borders.** 1px hairlines on cards and inputs, always — Wisy doesn't do borderless cards floating on shadow alone. Default `#E6E6E6`; accent `#CDD1FF` (lavender). Strong-emphasis blocks use a 1.5px or 2px black border for *brand moments* (the wordmark lockup, signature CTAs).

**Shadows.** Subtle, indigo-tinted at the base (rgba(16, 24, 64, x)) so they don't muddy the palette. Four levels: `xs` (1px line), `sm` (resting card), `md` (hovered card), `lg` (modal/menu). One special `--shadow-indigo` for the primary CTA on a light surface.

**Capsules vs. gradients.** Wisy uses **capsules** for protection — pills, badges, and rounded blocks on top of imagery. No gradient overlays. Text on photography sits inside a solid white or `#F0F1FF` capsule with `radius-pill` or `radius-lg`.

**Transparency & blur.** Used sparingly. The only "frosted" surface in the system is the mobile-app top bar over a live camera viewfinder — `backdrop-filter: blur(12px)` on a `rgba(255,255,255,0.7)` fill. Elsewhere, surfaces are opaque.

**Imagery vibe.** Warm-neutral, daylight-balanced, true-color. Real CPG shelves — beverages, snacks, household goods — shot in real stores. No moody color grading. No grain. No selective focus tricks. The point is "this is what your shelf looks like right now," so the imagery feels like ground truth.

**Corner radii.** Wisy is **generously rounded** for surfaces, **pill** for interactive things, **sharp** never. Standard scale: `4 / 8 / 12 / 20 / 28 / 40 / pill`. Cards default to `lg` (20px). Big brand-tile cards use `xl` (28px) or `2xl` (40px). Buttons, badges, chips, status pills — always `pill`. Inputs use `md` (12px). Avatars and logo containers are pure circles (`pill`).

**Cards.** White or `#F5F5F5` fill, 20px radius, 1px `#E6E6E6` border, `shadow-sm`. On hover, `shadow-md` + `#CDD1FF` border. Cards have generous internal padding — `var(--space-6)` (24px) minimum, often `var(--space-8)` (32px) for primary surfaces.

**Layout rules.** 12-column grid at desktop with 24px gutters. Mobile is single-column with 16px page padding. Wisy generally **doesn't** use sticky floating CTAs — actions live in their natural place in the flow. The only fixed element is the mobile app's bottom action bar. Marketing pages center max-width content at ~1200px on a white page.

---

## Iconography

**Approach.** Wisy is **light** on iconography overall — it prefers numbers, photographs, and short verbs to icon-led UI. When icons are present, they are stroke-style, 1.5px stroke weight, rounded line caps, single color (the foreground color of their context), at standard sizes 16 / 20 / 24px. Icons never appear in decorative grids of feature cards (a common AI-startup trope Wisy intentionally avoids).

**Set.** Wisy's product surfaces don't ship with a proprietary icon system in the provided assets. **For this design system we substitute [Lucide](https://lucide.dev/) (loaded via CDN)** — it matches Wisy's stroke style, rounded caps, and 24px viewBox conventions almost exactly. ⚠️ **Substitution flagged** — if you have the real production icon set, replace `<i data-lucide="...">` with the source SVGs.

**Loading.**
```html
<script src="https://unpkg.com/lucide@latest"></script>
<i data-lucide="camera"></i>
<script>lucide.createIcons();</script>
```

**Emoji.** Not used in product or marketing. Don't introduce them.

**Unicode glyphs.** The `:` (colon) is the only character with brand significance — it's part of the wordmark (`wisy:` / `w:`). Don't use the colon decoratively elsewhere; let it belong to the logo. Em-dashes `—` are used liberally in body copy.

**Logos provided** (in `assets/`):
- `Wisy_Logo_Indigo.png` — square mark `w:` indigo-on-black (1200×1200)
- `Wisy_Logo_Indigo_Transparent.png` — square mark `w:` indigo on transparent
- `Wisy_Logo_White.png` — square mark `w:` white on transparent (for dark backgrounds)
- `Wordmark_Indigo_Transparent.png` — horizontal `WISY:` wordmark, indigo
- `Brand_Style_Tile.png` — the canonical foundations reference (palette, type, lockups)

---

## Type substitution note

The brand specifies **Figtree** (primary) and **Roboto Mono** (secondary). Both are available on Google Fonts and are loaded via `@import` in `colors_and_type.css` — no local font files are required. ⚠️ **If your team licenses bespoke versions, drop the `.woff2` files into `fonts/` and replace the `@import` with `@font-face` declarations.**

---

## Caveats

- No production codebase or Figma was provided. UI kits are visual recreations from the brand tile + the public Wisy product model; component naming, exact spacing, and interaction details may differ from the real product.
- The product likely ships a proprietary icon set; Lucide is a substitute. Flag any mismatches.
- No slide template was provided, so no `slides/` directory was built. Ask if you want one (a Wisy-flavored deck template is trivial to add on top of these foundations).
