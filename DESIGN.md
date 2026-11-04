---
version: alpha
name: portfolio-rudy
description: Rudy's personal portfolio design system, inspired by Apple's sober style and made personal with a touch of green. A calm, airy portfolio interface. Full-width sections alternate light and dark canvases, framed by bold headlines with negative letter-spacing and a single Action Green (#00783c) interactive color. The UI stays quiet so the content can speak — no decorative gradients, no shadows on chrome, only one soft drop-shadow reserved for images resting on a surface.

colors:
  primary: "#00783c"
  primary-focus: "#008643"
  primary-on-dark: "#00ab56"
  ink: "#1d1d1f"
  body: "#1d1d1f"
  body-on-dark: "#ffffff"
  body-muted: "#cccccc"
  ink-muted-80: "#333333"
  ink-muted-48: "#7a7a7a"
  divider-soft: "#f0f0f0"
  hairline: "#e0e0e0"
  canvas: "#ffffff"
  canvas-parchment: "#f5f5f7"
  surface-pearl: "#fafafc"
  surface-tile-1: "#272729"
  surface-tile-2: "#2a2a2c"
  surface-tile-3: "#252527"
  surface-black: "#000000"
  surface-chip-translucent: "#d2d2d7"
  on-primary: "#ffffff"
  on-dark: "#ffffff"

typography:
  hero-display:
    fontFamily: "SF Pro Display, system-ui, -apple-system, sans-serif"
    fontSize: 56px
    fontWeight: 600
    lineHeight: 1.07
    letterSpacing: -0.28px
  display-lg:
    fontFamily: "SF Pro Display, system-ui, -apple-system, sans-serif"
    fontSize: 40px
    fontWeight: 600
    lineHeight: 1.1
    letterSpacing: 0
  display-md:
    fontFamily: "SF Pro Text, system-ui, -apple-system, sans-serif"
    fontSize: 34px
    fontWeight: 600
    lineHeight: 1.47
    letterSpacing: -0.374px
  lead:
    fontFamily: "SF Pro Display, system-ui, -apple-system, sans-serif"
    fontSize: 28px
    fontWeight: 400
    lineHeight: 1.14
    letterSpacing: 0.196px
  lead-airy:
    fontFamily: "SF Pro Text, system-ui, -apple-system, sans-serif"
    fontSize: 24px
    fontWeight: 300
    lineHeight: 1.5
    letterSpacing: 0
  tagline:
    fontFamily: "SF Pro Display, system-ui, -apple-system, sans-serif"
    fontSize: 21px
    fontWeight: 600
    lineHeight: 1.19
    letterSpacing: 0.231px
  body-strong:
    fontFamily: "SF Pro Text, system-ui, -apple-system, sans-serif"
    fontSize: 17px
    fontWeight: 600
    lineHeight: 1.24
    letterSpacing: -0.374px
  body:
    fontFamily: "SF Pro Text, system-ui, -apple-system, sans-serif"
    fontSize: 17px
    fontWeight: 400
    lineHeight: 1.47
    letterSpacing: -0.374px
  dense-link:
    fontFamily: "SF Pro Text, system-ui, -apple-system, sans-serif"
    fontSize: 17px
    fontWeight: 400
    lineHeight: 2.41
    letterSpacing: 0
  caption:
    fontFamily: "SF Pro Text, system-ui, -apple-system, sans-serif"
    fontSize: 14px
    fontWeight: 400
    lineHeight: 1.43
    letterSpacing: -0.224px
  caption-strong:
    fontFamily: "SF Pro Text, system-ui, -apple-system, sans-serif"
    fontSize: 14px
    fontWeight: 600
    lineHeight: 1.29
    letterSpacing: -0.224px
  button-large:
    fontFamily: "SF Pro Text, system-ui, -apple-system, sans-serif"
    fontSize: 18px
    fontWeight: 300
    lineHeight: 1.0
    letterSpacing: 0
  button-utility:
    fontFamily: "SF Pro Text, system-ui, -apple-system, sans-serif"
    fontSize: 14px
    fontWeight: 400
    lineHeight: 1.29
    letterSpacing: -0.224px
  fine-print:
    fontFamily: "SF Pro Text, system-ui, -apple-system, sans-serif"
    fontSize: 12px
    fontWeight: 400
    lineHeight: 1.0
    letterSpacing: -0.12px
  micro-legal:
    fontFamily: "SF Pro Text, system-ui, -apple-system, sans-serif"
    fontSize: 10px
    fontWeight: 400
    lineHeight: 1.3
    letterSpacing: -0.08px
  nav-link:
    fontFamily: "SF Pro Text, system-ui, -apple-system, sans-serif"
    fontSize: 12px
    fontWeight: 400
    lineHeight: 1.0
    letterSpacing: -0.12px

rounded:
  none: 0px
  xs: 5px
  sm: 8px
  md: 11px
  lg: 18px
  pill: 9999px
  full: 9999px

spacing:
  xxs: 4px
  xs: 8px
  sm: 12px
  md: 17px
  lg: 24px
  xl: 32px
  xxl: 48px
  section: 80px

components:
  button-primary:
    backgroundColor: "{colors.primary}"
    textColor: "{colors.on-primary}"
    typography: "{typography.body}"
    rounded: "{rounded.pill}"
    padding: 11px 22px
  button-primary-focus:
    backgroundColor: "{colors.primary}"
    textColor: "{colors.on-primary}"
    rounded: "{rounded.pill}"
  button-primary-active:
    backgroundColor: "{colors.primary}"
    textColor: "{colors.on-primary}"
    rounded: "{rounded.pill}"
  button-secondary-pill:
    backgroundColor: transparent
    textColor: "{colors.primary}"
    typography: "{typography.body}"
    rounded: "{rounded.pill}"
    padding: 11px 22px
  button-dark-utility:
    backgroundColor: "{colors.ink}"
    textColor: "{colors.on-dark}"
    typography: "{typography.button-utility}"
    rounded: "{rounded.sm}"
    padding: 8px 15px
  button-pearl-capsule:
    backgroundColor: "{colors.surface-pearl}"
    textColor: "{colors.ink-muted-80}"
    typography: "{typography.caption}"
    rounded: "{rounded.md}"
    padding: 8px 14px
  button-hero:
    backgroundColor: "{colors.primary}"
    textColor: "{colors.on-primary}"
    typography: "{typography.button-large}"
    rounded: "{rounded.pill}"
    padding: 14px 28px
  button-icon-circular:
    backgroundColor: "{colors.surface-chip-translucent}"
    textColor: "{colors.ink}"
    rounded: "{rounded.full}"
    size: 44px
  text-link:
    backgroundColor: transparent
    textColor: "{colors.primary}"
    typography: "{typography.body}"
  text-link-on-dark:
    backgroundColor: transparent
    textColor: "{colors.primary-on-dark}"
    typography: "{typography.body}"
  global-nav:
    backgroundColor: "{colors.surface-black}"
    textColor: "{colors.on-dark}"
    typography: "{typography.nav-link}"
    height: 44px
  sub-nav-frosted:
    backgroundColor: "{colors.canvas-parchment}"
    textColor: "{colors.ink}"
    typography: "{typography.tagline}"
    height: 52px
  section-tile-light:
    backgroundColor: "{colors.canvas}"
    textColor: "{colors.ink}"
    typography: "{typography.display-lg}"
    rounded: "{rounded.none}"
    padding: 80px
  section-tile-parchment:
    backgroundColor: "{colors.canvas-parchment}"
    textColor: "{colors.ink}"
    typography: "{typography.display-lg}"
    rounded: "{rounded.none}"
    padding: 80px
  section-tile-dark:
    backgroundColor: "{colors.surface-tile-1}"
    textColor: "{colors.on-dark}"
    typography: "{typography.display-lg}"
    rounded: "{rounded.none}"
    padding: 80px
  section-tile-dark-2:
    backgroundColor: "{colors.surface-tile-2}"
    textColor: "{colors.on-dark}"
    rounded: "{rounded.none}"
  section-tile-dark-3:
    backgroundColor: "{colors.surface-tile-3}"
    textColor: "{colors.on-dark}"
    rounded: "{rounded.none}"
  project-card:
    backgroundColor: "{colors.canvas}"
    textColor: "{colors.ink}"
    typography: "{typography.body-strong}"
    rounded: "{rounded.lg}"
    padding: 24px
  tag-chip:
    backgroundColor: "{colors.canvas}"
    textColor: "{colors.ink}"
    typography: "{typography.caption}"
    rounded: "{rounded.pill}"
    padding: 12px 16px
  tag-chip-selected:
    backgroundColor: "{colors.canvas}"
    textColor: "{colors.ink}"
    rounded: "{rounded.pill}"
  search-input:
    backgroundColor: "{colors.canvas}"
    textColor: "{colors.ink}"
    typography: "{typography.body}"
    rounded: "{rounded.pill}"
    padding: 12px 20px
    height: 44px
  floating-sticky-bar:
    backgroundColor: "{colors.canvas-parchment}"
    textColor: "{colors.ink}"
    typography: "{typography.body}"
    height: 64px
    padding: 12px 32px
  quote-card:
    backgroundColor: "{colors.surface-tile-1}"
    textColor: "{colors.on-dark}"
    typography: "{typography.display-lg}"
    rounded: "{rounded.none}"
    padding: 80px
  footer:
    backgroundColor: "{colors.canvas-parchment}"
    textColor: "{colors.ink-muted-80}"
    typography: "{typography.fine-print}"
    padding: 64px
---

## Overview

This is Rudy's own portfolio design system. It borrows the sober, airy spirit of Apple's style and makes it personal with one signature touch: a single Action Green accent. It is built on **clear content framed by near-invisible UI**. Every page is a stack of full-width sections — alternating light and dark canvases, each centered on a headline, a one-line tagline, small green pill CTAs, and an optional image. Nothing competes with the content. Typography is confident but quiet; color is either pure white, an off-white parchment, or a near-black tile; interactive elements are a single, quiet green.

Density is deliberately low. Each section breathes, and there is no decorative chrome — no borders, no gradients, no decorative frames, no shadows on headlines. Elevation appears only when an image rests on a surface (a single soft `rgba(0, 0, 0, 0.22) 3px 5px 30px` drop for visual weight). The result feels like a calm gallery: the wall disappears and the content takes over.

Content pages (projects, skills) keep the same chassis but switch modes: a tight grid of white utility cards at `{rounded.lg}` (18px) radius with a thin border, paired with an optional thin sub-nav strip. Darker sections can be used for a more editorial tone. Across every page the typographic system, spacing rhythm, and the single green accent stay consistent — this is one design language expressed at different volumes.

**Key Characteristics:**

- Content-first presentation; UI recedes so the content can speak.
- Alternating full-bleed tile sections: white/parchment ↔ near-black, with the color change itself acting as the section divider.
- Single green accent (`{colors.primary}` — #00783c) carries every interactive element. No second brand color exists.
- Two button grammars: small green pill CTAs (`{rounded.pill}`) and compact utility rects (`{rounded.sm}`).
- A display face for headlines and a text face for body — negative letter-spacing at display sizes for a tight, confident headline feel.
- Whisper-soft elevation used only when an image needs to breathe — exactly one drop-shadow in the entire system.
- Tight two-row nav: slim `{component.global-nav}` + page-specific `{component.sub-nav-frosted}` with persistent right-aligned primary CTA.
- Section rhythm across multiple pages: light hero → dark tile → light utility tile → dark tile → parchment footer — a predictable pulse.

## Colors

> **Scope:** the color system is identical across every page of the portfolio; only the mix of light and dark sections differs.

### Brand & Accent

- **Action Green** (`{colors.primary}` — #00783c): The single brand-level interactive color. All text links, all green pill CTAs, and the focus ring root. This is the portfolio's quiet but universal "click me" signal. Press state shifts to a slightly darker variant via the active scale transform rather than a hex change.
- **Focus Green** (`{colors.primary-focus}` — #008643): A marginally brighter sibling of Action Green, reserved for the keyboard focus ring on buttons (`outline: 2px solid`).
- **Light Green** (`{colors.primary-on-dark}` — #00ab56): A brighter green used on dark surfaces for in-copy links and inline callouts, where Action Green would disappear against the tile background.

### Surface

- **Pure White** (`{colors.canvas}` — #ffffff): The dominant canvas. Content, utility cards, card grids.
- **Parchment** (`{colors.canvas-parchment}` — #f5f5f7): The portfolio's signature off-white. Used for alternating light tiles, footer region, and the default page canvas in utility sections. Just different enough from white to create rhythm.
- **Pearl Button** (`{colors.surface-pearl}` — #fafafc): A near-white used as the fill for secondary "ghost" buttons — lighter than the parchment canvas so the button still reads as a button against `{colors.canvas-parchment}`.
- **Near-Black Tile 1** (`{colors.surface-tile-1}` — #272729): The primary dark-tile surface.
- **Near-Black Tile 2** (`{colors.surface-tile-2}` — #2a2a2c): A micro-step lighter — used where a dark tile sits directly above or below Tile 1 to create the faintest separation.
- **Near-Black Tile 3** (`{colors.surface-tile-3}` — #252527): A micro-step darker — used at the bottom of the stack and in embedded video/player frames.
- **Pure Black** (`{colors.surface-black}` — #000000): Reserved for true void — video player backgrounds, edge-to-edge photographic overlays, the global nav bar background.
- **Translucent Chip Gray** (`{colors.surface-chip-translucent}` — #d2d2d7): The base hex of the translucent gray chip used over photography for circular control buttons. In production, applied at ~64% alpha as `rgba(210, 210, 215, 0.64)`.

### Text

- **Near-Black Ink** (`{colors.ink}` — #1d1d1f): The voice of every headline, every body paragraph, and the dark utility button's fill. Chosen instead of pure black to keep the page feeling photographic rather than printed.
- **Body** (`{colors.body}` — #1d1d1f): Same hex as ink — the portfolio uses one near-black tone for all text on light surfaces.
- **Body On Dark** (`{colors.body-on-dark}` — #ffffff): All text on dark tiles and on the global nav bar.
- **Body Muted** (`{colors.body-muted}` — #cccccc): Secondary copy on dark tiles where pure white would be too loud.
- **Ink Muted 80** (`{colors.ink-muted-80}` — #333333): Body text on the white Pearl Button surface — slightly softer than pure black.
- **Ink Muted 48** (`{colors.ink-muted-48}` — #7a7a7a): Disabled button text and legal fine-print.

### Hairlines & Borders

- **Divider Soft** (`{colors.divider-soft}` — #f0f0f0): The "border" tone on secondary buttons — functions as a ring shadow rather than a hard line. In production, often applied as `rgba(0, 0, 0, 0.04)`.
- **Hairline** (`{colors.hairline}` — #e0e0e0): The 1px hairline border on utility cards and option chips.

### Brand Gradient

**No decorative gradients.** Any atmospheric depth comes from the images themselves, never from a CSS gradient overlay. The system defines zero gradient tokens: sobriety is the rule.

## Typography

### Font Family

- **Display**: `SF Pro Display, system-ui, -apple-system, sans-serif` — the display face, used for sizes ≥ 19px. Defines the voice of every headline.
- **Body / UI**: `SF Pro Text, system-ui, -apple-system, sans-serif` — the text face, used for body copy, captions, buttons, and links below 20px.
- **OpenType features**: `font-variant-numeric: numerator` is enabled on numeric links (tables, figures). Display sizes rely on tight tracking rather than contextual ligatures.

### Hierarchy

| Token                         | Size | Weight | Line Height | Letter Spacing | Use                                                    |
| ----------------------------- | ---- | ------ | ----------- | -------------- | ------------------------------------------------------ |
| `{typography.hero-display}`   | 56px | 600    | 1.07        | -0.28px        | Hero headline; the signature tight tracking            |
| `{typography.display-lg}`     | 40px | 600    | 1.10        | 0              | Tile headlines atop every section tile                 |
| `{typography.display-md}`     | 34px | 600    | 1.47        | -0.374px       | Section heads (text face at display proportions)       |
| `{typography.lead}`           | 28px | 400    | 1.14        | 0.196px        | Section tile subcopy                                   |
| `{typography.lead-airy}`      | 24px | 300    | 1.5         | 0              | Airy lead paragraphs (the rare weight 300)             |
| `{typography.tagline}`        | 21px | 600    | 1.19        | 0.231px        | Sub-tile tagline; sub-nav page name                    |
| `{typography.body-strong}`    | 17px | 600    | 1.24        | -0.374px       | Inline strong emphasis                                 |
| `{typography.body}`           | 17px | 400    | 1.47        | -0.374px       | Default paragraph                                      |
| `{typography.dense-link}`     | 17px | 400    | 2.41        | 0              | Footer / utility link lists (relaxed leading)          |
| `{typography.caption}`        | 14px | 400    | 1.43        | -0.224px       | Secondary captions, button text                        |
| `{typography.caption-strong}` | 14px | 600    | 1.29        | -0.224px       | Emphasized captions                                    |
| `{typography.button-large}`   | 18px | 300    | 1.0         | 0              | Large hero CTAs (the rare weight 300)                  |
| `{typography.button-utility}` | 14px | 400    | 1.29        | -0.224px       | Utility/nav button labels                              |
| `{typography.fine-print}`     | 12px | 400    | 1.0         | -0.12px        | Fine-print, footer body                                |
| `{typography.micro-legal}`    | 10px | 400    | 1.3         | -0.08px        | Micro legal disclaimers                                |
| `{typography.nav-link}`       | 12px | 400    | 1.0         | -0.12px        | Global nav menu items                                  |

### Principles

- **Negative letter-spacing at display sizes.** Every headline at 17px and up carries a slight tracking tighten (`-0.12 → -0.374px`). This produces a tight, confident headline cadence. Never used at 12px or below.
- **Body copy at 17px, not 16px.** The portfolio breaks the usual convention and runs paragraph text at 17px. The extra pixel gives the page a calm "reading, not scanning" pace.
- **Weight 300 is real and rare.** Used deliberately on a handful of large-size reads (`{typography.button-large}` at 18px/300 and `{typography.lead-airy}` at 24px/300). It's not an accident — it's a light-atmosphere cue reserved for moments where the content should feel airy.
- **Weight 600, not 700, for headlines.** Headlines and `{typography.tagline}` (21px) sit at weight 600. No token uses weight 700 today; it stays in the ladder for the rare case where a touch more assertion is needed.
- **Line-height is context-specific.** Display sizes use 1.07–1.19 (tight). Body uses 1.47. Utility link stacks in the footer use an unusually relaxed 2.41 (`{typography.dense-link}`). The 2.41 is not a bug — it's how the footer's dense link columns breathe.
- **Weight 500 is deliberately absent.** The ladder is 300 / 400 / 600 / 700. Mid-weight readings always use 600.

### Note on Font Substitutes

SF Pro is not available on every platform. When it is missing:

- Use `system-ui, -apple-system, BlinkMacSystemFont` as the first stack entry — it resolves to the platform's native UI font, or to SF Pro where it is installed.
- Elsewhere, **Inter** (Google Fonts, variable) is the closest open-source equivalent. Inter at weight 600 with `font-feature-settings: "ss03"` approximates SF Pro's rounded "a" character.
- Nudge `letter-spacing` down by `-0.01em` on display sizes to re-create the tight headline feel; Inter's default tracking runs slightly wider than SF Pro.
- For body text, tighten line-height by `0.03` (from 1.47 → 1.44) when substituting Inter — Inter's taller x-height needs less leading.

## Layout

### Spacing System

- **Base unit:** 8px. Sub-base values (2, 4, 5, 6, 7) are used for tight typographic adjustments; structural layout snaps to 8/12/16/20/24.
- **Tokens:** `{spacing.xxs}` 4px · `{spacing.xs}` 8px · `{spacing.sm}` 12px · `{spacing.md}` 17px · `{spacing.lg}` 24px · `{spacing.xl}` 32px · `{spacing.xxl}` 48px · `{spacing.section}` 80px.
- **Section vertical padding:** `{spacing.section}` (80px) inside a section tile; tiles stack edge-to-edge with 0 gap (the color change provides the break).
- **Card padding:** `{spacing.lg}` (24px) inside utility grid cards.
- **Button padding:** 8–11px vertical, 15–22px horizontal.
- **Universal rhythm constants:** the 17px body line-height multiplier (~25px line) and 21px tagline size show up on every page.

### Grid & Container

- **Max content width:** ~980px on text-heavy pages, ~1440px on card grids, full-bleed for section tiles.
- **Column patterns:** 3 to 5 column utility card grid; 2-column side-by-side tiles for occasional sections; single-column centered stack on hero tiles.
- **Gutters:** 20–24px between cards in a utility grid.

### Whitespace Philosophy

Whitespace is the content's pedestal. Every tile begins with at least 64px of air above its headline and 48–64px below. Images are never crowded; the nearest content to an image is at least 40px away. The footer is the only area that breaks this — there, the layout goes deliberately dense to make the full site structure visible at a glance.

## Elevation & Depth

| Level          | Treatment                                   | Use                                                                 |
| -------------- | ------------------------------------------- | ------------------------------------------------------------------- |
| Flat           | No shadow, no border                        | Full-bleed tiles, global nav, footer, body sections                 |
| Soft hairline  | 1px `rgba(0, 0, 0, 0.08)` border            | Utility cards, sub-nav frosted-glass separator                      |
| Backdrop blur  | `backdrop-filter: blur(N)` on Parchment 80% | Sub-nav and the floating sticky bar                                 |
| Image shadow   | `rgba(0, 0, 0, 0.22) 3px 5px 30px 0`        | Images resting on a surface (the only true "shadow" in the system)  |

**Shadow philosophy.** The system uses **exactly one** drop-shadow, and it is applied to images resting on a surface — never to cards, never to buttons, never to text. Elevation in the UI comes from (a) surface-color change (light tile ↔ dark tile) and (b) backdrop-blur on sticky bars. The single shadow is about giving the image weight, not about UI hierarchy.

### Decorative Depth

- **Atmospheric imagery** (photographic backgrounds) supplies mood; no CSS gradient involved.
- **Edge-to-edge tile alternation** creates rhythm without borders or shadows — the color change itself is the divider.
- **Backdrop-filter blur** on `{component.sub-nav-frosted}` and `{component.floating-sticky-bar}` creates a "floating over content" effect that's functional, not decorative.

## Shapes

### Border Radius Scale

| Token            | Value        | Use                                                                                                   |
| ---------------- | ------------ | ----------------------------------------------------------------------------------------------------- |
| `{rounded.none}` | 0px          | Full-bleed section tiles (no corner rounding)                                                         |
| `{rounded.xs}`   | 5px          | Inline links when styled as subtle chips (rare)                                                       |
| `{rounded.sm}`   | 8px          | Dark utility buttons (compact actions), inline card imagery                                           |
| `{rounded.md}`   | 11px         | White Pearl Button capsules                                                                           |
| `{rounded.lg}`   | 18px         | Utility cards, card grid cards                                                                        |
| `{rounded.pill}` | 9999px       | Primary green pill CTAs, sub-nav CTA, option chips, search input — the signature pill                 |
| `{rounded.full}` | 9999px / 50% | Circular control chips floating over photography                                                      |

### Photography Geometry

- **Hero imagery**: full-bleed, 21:9 or taller on the home page; 16:9 on other pages. Images can sit on a tinted surface that becomes the tile background.
- **Images on a surface**: PNG/WebP with transparency; rest on a surface tile and pick up the system shadow.
- **Card grid**: square 1:1 crops at `{rounded.lg}` (18px) radius, light neutral backgrounds, subject centered with 20–40px internal padding.
- **No rounded imagery in hero tiles** — images are full-bleed rectangular. Rounding (`{rounded.sm}`, `{rounded.lg}`) appears only on inline card imagery.
- Lazy-loading via responsive `srcset` and `sizes` across all breakpoints; optimized WebP.

## Components

### Top Navigation

**`global-nav`** — Persistent, ultra-thin black nav bar pinned to the top of every page. Background `{colors.surface-black}`, height 44px, text `{colors.on-dark}` in `{typography.nav-link}` (12px / 400 / -0.12px tracking). Links are quiet, spaced ~20px apart, running edge-to-edge across the top. Right-aligned cluster: optional utility icons — always visible. On mobile, collapses to hamburger at ~834px and the site name centers.

**`sub-nav-frosted`** — Page-specific nav that sticks below the global nav. Background `{colors.canvas-parchment}` at 80% opacity with backdrop-filter blur, creating a frosted-glass effect. Height 52px. Content on left: page name (e.g. "Projects", "Skills") in `{typography.tagline}` (21px / 600). Content right: inline nav links in `{typography.button-utility}` (14px), ending in a persistent `{component.button-primary}` (main call to action) or a utility link.

### Buttons

**`button-primary`** — The signature action. Background `{colors.primary}` (Action Green #00783c), text `{colors.on-primary}` in `{typography.body}` (17px / 400), rounded `{rounded.pill}` (full pill — capsule-shaped), padding 11px × 22px. The full-pill radius IS the action signal.

- Active state: `{component.button-primary-active}` — `transform: scale(0.95)` (the system-wide micro-interaction).
- Focus state: `{component.button-primary-focus}` — 2px solid `{colors.primary-focus}` outline.

**`button-secondary-pill`** — Used as the second CTA when two green pills appear together. Background transparent, text `{colors.primary}`, 1px solid `{colors.primary}` border, rounded `{rounded.pill}`, padding 11px × 22px. Reads as a "ghost pill."

**`button-dark-utility`** — Compact actions in the nav. Background `{colors.ink}` (#1d1d1f), text `{colors.on-dark}` in `{typography.button-utility}` (14px / 400 / -0.224px tracking), rounded `{rounded.sm}` (8px), padding 8px × 15px. Active state shrinks via `transform: scale(0.95)`.

**`button-pearl-capsule`** — Card secondary button. Background `{colors.surface-pearl}` (#fafafc), text `{colors.ink-muted-80}` in `{typography.caption}` (14px), 3px solid `{colors.divider-soft}` border (functions as a soft ring rather than a visible line), rounded `{rounded.md}` (11px), padding 8px × 14px.

**`button-hero`** — A larger primary CTA used on hero sections. Same Action Green background and `{colors.on-primary}` text as `{component.button-primary}`, but with `{typography.button-large}` (18px / 300 — note the rare weight 300) and slightly more padding (14px × 28px). Used sparingly on the home page.

**`button-icon-circular`** — Floats over photography. 44 × 44px, background `{colors.surface-chip-translucent}` at ~64% alpha, icon in `{colors.ink}`, rounded `{rounded.full}`. Used for carousel controls, close buttons, and in-image controls.

**`text-link`** — Inline body links in `{colors.primary}` (Action Green). Underlined or non-underlined per context.

**`text-link-on-dark`** — Inline body links on dark tiles in `{colors.primary-on-dark}` (Light Green #00ab56) — Action Green would disappear against `{colors.surface-tile-1}`.

### Cards & Containers

**`section-tile-light`** — Full-bleed light tile. Background `{colors.canvas}` (white), text `{colors.ink}`, rounded `{rounded.none}` (0 — tiles touch edges), vertical padding `{spacing.section}` (80px). Centered stack: section title in `{typography.display-lg}` (40px / 600) → one-line tagline in `{typography.lead}` (28px / 400) → one or two `{component.button-primary}` CTAs → optional image resting on the surface with the system shadow.

**`section-tile-parchment`** — Same as `{component.section-tile-light}` but on `{colors.canvas-parchment}` (#f5f5f7). Used to break two consecutive white tiles.

**`section-tile-dark`** — Full-bleed dark tile. Background `{colors.surface-tile-1}` (#272729), text `{colors.on-dark}`, rounded `{rounded.none}`, vertical padding `{spacing.section}` (80px). Same content stack as the light tile but with `{component.text-link-on-dark}` for inline copy and `{component.button-primary}` (Action Green still works on the dark surface). Used as the alternating dark band.

**`section-tile-dark-2`** — Variant on `{colors.surface-tile-2}` (#2a2a2c). Used where a dark tile sits directly above or below `{component.section-tile-dark}` to create the faintest separation through micro-step lightness change.

**`section-tile-dark-3`** — Variant on `{colors.surface-tile-3}` (#252527). Used at the bottom of the stack and in embedded video/player frames.

**`project-card`** — Used in card grids (e.g. projects). Background `{colors.canvas}` (white), 1px solid `{colors.hairline}` border, rounded `{rounded.lg}` (18px), padding `{spacing.lg}` (24px). Top: image (1:1 crop with `{rounded.sm}` (8px) inner image radius). Below: card title in `{typography.body-strong}` (17px / 600), short description in `{typography.body}` (17px / 400), and a `{component.text-link}` ("Learn more"). No shadow by default; an image resting on a surface carries the system shadow.

**`tag-chip`** — Pill-shaped tappable cell (e.g. filters or tags). Background `{colors.canvas}`, text `{colors.ink}` in `{typography.caption}`, rounded `{rounded.pill}`, padding 12px × 16px. Contains a small icon + label. Arranged in a grid of 4–5 options per row.

**`tag-chip-selected`** — Selected state. Border upgrades to 2px solid `{colors.primary-focus}`. Same shape, same content.

**`quote-card`** — A photographic-canvas section (e.g. a quote or a key message). Dark photographic backdrop with `{colors.surface-tile-1}` as the fallback color, centered white-text headline in `{typography.display-lg}` (40px), optional small pictogram above the headline, single `{component.button-primary}` below. Padding `{spacing.section}` (80px).

**`floating-sticky-bar`** — Floats at the bottom of the viewport during scroll. Background `{colors.canvas-parchment}` at 80% opacity with `backdrop-filter: blur(N)`, height 64px, padding 12px × 32px. Left: short message in `{typography.body}`. Right: `{component.button-primary}` (main call to action).

### Inputs & Forms

**`search-input`** — The search input. Background `{colors.canvas}`, text `{colors.ink}` in `{typography.body}` (17px), 1px solid `rgba(0, 0, 0, 0.08)` border, rounded `{rounded.pill}` (full pill — search is also pill-shaped, matching the CTA grammar), padding 12px × 20px, height 44px. Leading icon: search glyph at 14px, muted tint.

Error and validation states are not documented yet.

### Footer

**`footer`** — Background `{colors.canvas-parchment}` (#f5f5f7), text `{colors.ink-muted-80}`. Link columns in `{typography.dense-link}` (17px / 400 / 2.41 line-height — the relaxed leading is what makes the dense columns scannable). Column headings in `{typography.caption-strong}` (14px / 600). Legal row at the very bottom in `{typography.fine-print}` (12px / 400) with `{colors.ink-muted-48}` text. Vertical padding 64px.

## Do's and Don'ts

### Do

- Use `{colors.primary}` (Action Green #00783c) for every interactive element — links, pill CTAs, focus signals — and nothing else. The single accent is non-negotiable.
- Set headlines in `{typography.hero-display}` or `{typography.display-lg}` with negative letter-spacing (`-0.28 → -0.374px`) to get the signature tight cadence.
- Run body copy at `{typography.body}` (17px / 400 / 1.47 / -0.374px) — not 16px. The extra pixel defines the portfolio's reading pace.
- Alternate `{component.section-tile-light}` (or parchment) and `{component.section-tile-dark}` for full-bleed section rhythm. The color change IS the divider.
- Reserve `{rounded.pill}` for the primary green CTA and any other element that should read as an "action" (option chips, search input, sticky bar CTA).
- Apply the single image shadow (`rgba(0, 0, 0, 0.22) 3px 5px 30px`) only to images resting on a surface — never on cards, buttons, or text.
- Use `transform: scale(0.95)` as the active/press state on every button — it's the system-wide micro-interaction.
- Keep the global nav `{colors.surface-black}` (true black) — it's the only place pure black appears on most pages.

### Don't

- Don't introduce a second accent color; every "click me" signal is `{colors.primary}` (Action Green).
- Don't add shadows to cards, buttons, or text — shadow is reserved for images.
- Don't use gradients as decorative backgrounds; atmosphere comes from photography.
- Don't set body copy at weight 500 — the weight ladder is 300 / 400 / 600 / 700, with 500 deliberately absent. Body is always 400; strong inline is 600; display is 600.
- Don't round full-bleed tiles — tiles are rectangular and edge-to-edge; the color change is the divider.
- Don't tighten line-height below 1.47 for body copy — the editorial leading is part of the portfolio's identity.
- Don't mix radii grammars — use `{rounded.sm}` for compact utility, `{rounded.lg}` for utility cards, `{rounded.pill}` for pills, and nothing in between (except the rare `{rounded.md}` Pearl Button).
- Don't use `{colors.primary-on-dark}` (Light Green) on light surfaces — it's the dark-tile-only variant. Action Green is for light surfaces.

## Responsive Behavior

### Breakpoints

| Name             | Width       | Key Changes                                                                                           |
| ---------------- | ----------- | ----------------------------------------------------------------------------------------------------- |
| Small phone      | ≤ 419px     | Single-column tiles; sub-nav collapses to page name + primary CTA only; hero typography drops to 28px |
| Phone            | 420–640px   | Single-column stack; images scale to 80% of tile width; hero h1 drops to 34px                         |
| Large phone      | 641–735px   | Tiles transition to tighter padding (48px vertical vs 80px); fine-print wraps                         |
| Tablet portrait  | 736–833px   | Global nav collapses to hamburger; sub-nav hides inline links, keeps primary CTA                      |
| Tablet landscape | 834–1023px  | Global nav returns fully expanded; 3-column utility grids become 2-column                             |
| Small desktop    | 1024–1068px | Section tiles use 2/3 width with margin gutters; hero h1 stays at 40px                                |
| Desktop          | 1069–1440px | Full layout; 4–5 column card grids; 1440px content max                                                |
| Wide desktop     | ≥ 1441px    | Content locks at 1440px, margins absorb extra width                                                   |

The structural breakpoints that matter for agents: 1440px (content lock), 1068px (small-desktop), 833px (tablet landscape switch), 734px (tablet portrait), 640px (phone), 480px (small phone).

### Touch Targets

- Minimum 44 × 44px. `{component.button-primary}` lands at ~44 × 100px (with the full-pill radius making the visible hit area more generous than the label suggests).
- `{component.button-icon-circular}` is exactly 44 × 44px.
- Global nav utility links are smaller (~32 × 80px) — they deliberately sit at a tighter target because they're precision desktop actions, and the mobile hamburger replaces them at ≤ 833px.

### Collapsing Strategy

- **Global nav**: full horizontal link row on desktop → collapses to site name + hamburger at 834px and below.
- **Sub-nav**: page name + inline links + primary CTA → page name + primary CTA only at mobile; inline links move into a hamburger tray.
- **Section tiles**: stack from 2-column to 1-column at 834px; vertical padding tightens from 80px → 48px at small-phone.
- **Utility card grids**: 5-col → 4-col (1440px) → 3-col (1068px) → 2-col (834px) → 1-col (640px).
- **Hero typography**: `{typography.hero-display}` (56px) → `{typography.display-lg}` (40px) at 1068px → 34px at 640px → 28px at 419px.

### Image Behavior

- All imagery uses responsive `srcset` with breakpoint-matched crops.
- Hero photography may switch art direction at mobile (e.g. a landscape photo crops to a taller aspect ratio on mobile, framing the subject differently).
- Images maintain their 1:1 or 4:3 aspect ratios across breakpoints; only scale changes.
- Lazy-loading is default; the above-fold hero loads eagerly.

## Iteration Guide

1. Focus on ONE component at a time. Reference its YAML key directly (`{component.section-tile-dark}`, `{component.search-input}`).
2. Variants of an existing component (`-active`, `-focus`, `-2`, `-3`) live as separate entries in `components:`.
3. Use `{token.refs}` everywhere — never inline hex.
4. Never document hover. Default and Active/Pressed states only.
5. Display headlines stay in the display face at 600 with negative letter-spacing. Body stays in the text face at 400 at 17px. The boundary is unbreakable.
6. The single drop-shadow (`rgba(0, 0, 0, 0.22) 3px 5px 30px`) is reserved for images only.
7. When in doubt about emphasis: alternate surface (light → dark tile) before adding chrome.

## Known Gaps

- Form validation and error states are not documented yet; only the neutral search input is documented.
- Embedded video/player frames use `{colors.surface-black}`; interior player controls are not documented (they're a platform widget, not a web-design token).
- Some component content is dynamic (rotating hero content) and its specific copy varies per page — component specs name the structure, not the rotating content.
- Dark-mode counterparts for utility cards are not documented yet; the system documented is the light-dominant variant used by default.
- Atmospheric photography is a content asset, not a design token; the documented `{component.quote-card}` describes the structural surface only.
- The exact backdrop-filter blur radius on `{component.sub-nav-frosted}` and `{component.floating-sticky-bar}` is platform-dependent; production CSS uses `saturate(180%) blur(20px)` as a typical baseline but the value isn't formalized as a token.
