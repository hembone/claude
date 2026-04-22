# Visual Identity

## Color Palette

A warm, paper-like palette inspired by parchment, aged linen, and dried ink. The background feels like a calm workspace — not a blank screen. Terracotta is the sole accent: energetic enough to draw the eye, grounded enough to stay out of the way. The overall mood is artisanal-calm, not sterile SaaS.

### Primary Colors

| Token | Hex | Usage |
|-------|-----|-------|
| `--paper` | `#faf7f2` | Primary page background |
| `--paper-2` | `#f2ece1` | Cards, toolbars, secondary surfaces |
| `--paper-3` | `#e8dfd1` | Deeper surface, hover states, dividers |
| `--white` | `#fffdf8` | Panel white, card interiors |
| `--ink` | `#2d2a26` | Primary text, headings, logo "ez" |
| `--ink-2` | `#4a453e` | Secondary text, labels |
| `--ink-3` | `#7a7268` | Tertiary/muted text, icons, placeholders |
| `--rule` | `#d9cfbf` | Borders, dividers, table rules |

### Accent Colors

| Token | Hex | Usage |
|-------|-----|-------|
| `--accent` | `#d4704a` | Terracotta — primary CTAs, active states, logo "Listr", highlights |
| `--accent-deep` | `#b25939` | Hover and pressed states for accent elements |
| `--accent-soft` | `#f3d4c2` | Tinted accent backgrounds (selected rows, badges) |

### Supporting Colors

| Token | Hex | Usage |
|-------|-----|-------|
| `--sage` | `#7a8a6b` | Secondary supporting color, "live" status backgrounds |
| `--ochre` | `#c9a961` | Supporting color, callout stickers, highlight accents |

### Color Usage Rules

- Backgrounds are always warm paper tones — never cold gray or pure white
- Text uses warm ink tones for a softer, less harsh contrast than pure black
- A single accent (terracotta) handles all interactive elements — buttons, links, active states, focus rings
- Sage and ochre are supporting colors only — never used for primary interactive elements
- Overall tone: ~70% paper/warm white, ~15% ink tones, ~10% accent, ~5% sage/ochre

## Typography

Three typefaces, each with a distinct role. Together they create a layered system: warmth from the serif, utility from the sans, precision from the mono.

### Display — Instrument Serif
**Source:** Google Fonts (`Instrument Serif`, italic weight)
- Used for: Hero headings, section headers, step numbers, the "ez" in the logo wordmark
- Weight: 400 (regular), italic variant for personality
- Why: Humanist and warm. The italic style adds an artisanal, handcrafted quality without being precious. Pairs with Geist to balance approachability and utility.

**Usage examples:** `h1.display`, section `h2`, `.serif-i` italic decorative text, large step numerals

### UI Sans-serif — Geist
**Source:** Google Fonts (`Geist`, weights 400/500/600/700)
- Used for: Body copy, navigation, buttons, labels, the "Listr" in the logo wordmark
- Weights: 400 (body), 500 (emphasis), 600/700 (headings, brand name, CTAs)
- Why: Clean geometric sans-serif with excellent legibility at small sizes. Modern but not cold. Default for all UI text.

**Usage examples:** Body copy, nav links, button labels, form inputs, table cells

### Monospace — JetBrains Mono
**Source:** Google Fonts (`JetBrains Mono`, weights 400/500)
- Used for: Technical labels, dimension badges, SKU references, status chips, kicker labels, metadata
- Style: Uppercase, `letter-spacing: 0.04–0.12em` depending on context, 10–12px
- Why: Provides a precise, tool-like quality for data and labels. Anchors the "serious tool" feeling without making the UI feel cold.

**Usage examples:** Ratio labels (`4:3`, `1:1`), SKU codes, section kicker labels (`/ 01 — CROP`), dimension badges

### Type Rules

- Display headings: Instrument Serif, sentence case, `-0.01–0.02em` letter spacing
- Body: Geist Regular, 17px base, `line-height: 1.55`
- Technical metadata: JetBrains Mono, uppercase, generous letter spacing
- No all-caps for body copy or section headings — uppercase is reserved for mono labels only
- Text is left-aligned except for centered CTA sections

## Logo

### Wordmark Treatment

The logo is a typographic wordmark combining two typefaces:

- **"ez"** — Instrument Serif, italic, `--ink` (#2d2a26)
- **"Listr"** — Geist Bold (700), `--accent` (#d4704a), `font-size: 0.78em`, `margin-left: 2px`

The contrast between the serif italic and the geometric bold creates the brand character in miniature: artisanal warmth + practical utility.

### Usage Guidelines

- **Primary:** Wordmark on `--paper` or `--white` backgrounds
- **Reversed:** Wordmark on `--ink` dark backgrounds — "ez" in `--paper`, "Listr" in `--accent`
- **Minimum clear space:** Equal to the cap-height of the "L" on all sides
- **Minimum size:** 80px wide for digital use
- **Never:** Stretch, rotate, change typefaces, or apply drop shadows. Do not recolor "Listr" to anything other than `--accent`.
- **Favicon / icon:** The "ez" lettermark in Instrument Serif italic, or an abstract mark derived from the wordmark

## Design Aesthetic

### Surface and Texture

- **Grain overlay:** A subtle paper-grain texture at 35% opacity, `mix-blend-mode: multiply`, applied as a fixed overlay across the entire page. This gives the UI a tactile, printed quality.
- **Backgrounds:** Always warm paper tones. Primary content areas use `--paper` (#faf7f2). Cards and panels use `--white` (#fffdf8) or `--paper-2` (#f2ece1).
- **Canvas/grid backgrounds:** Interactive tool areas (crop canvas, mockup stage) use a fine dot or line grid in `--paper-2` on `--white` to evoke a designer's sketchpad.

### Shape and Structure

- **Border radius:** 14–18px for cards and panels; 6–10px for inner elements; `999px` (pill) for buttons and tags
- **Borders:** `1px solid var(--rule)` — warm, not harsh. Used consistently on cards, inputs, and dividers.
- **Shadows:** Warm-toned, low-opacity. `rgba(45,42,38, .12–.25)` — never cool gray box shadows.
- **Buttons:** Pill-shaped (`border-radius: 999px`). Primary = terracotta fill. Ghost = transparent with `--rule` border.
- **Status chips:** Pill or small rounded rectangle. Monospace type, uppercase.

### Imagery Style

#### Product Screenshots
- Show real Etsy seller content loaded in the tools — listings, photos, tags, prices. Never empty-state UIs.
- Warm paper backgrounds behind UI screenshots. Avoid floating on pure white.
- Annotations (callouts, step numbers) in `--accent` terracotta or `--ink`.

#### Demo and Social Imagery
- Before/after comparisons: messy unformatted photos vs. polished listing images
- Step-by-step sequences (3–4 frames) showing a workflow from raw photo to published listing
- Tool UI is the hero of every image — not lifestyle photography or generic stock

#### What to Avoid Visually
- Cold blue, gray, or navy palettes — they fight the brand's warm character
- Inter or generic system sans-serifs in marketing graphics (use Geist/Instrument Serif)
- Stock photography of entrepreneurs at laptops
- Heavy drop shadows, glossy effects, or gradients on solid UI elements
- Dark-mode / neon aesthetics — ezListr is explicitly a daylight, calm-workspace tool
