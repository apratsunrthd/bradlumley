---
name: Brad Lumley
description: Personal identity page and side-project launchpad for bradlumley.com
colors:
  midnight: "#0f172a"
  ink: "#e2e8f0"
  slate-muted: "#94a3b8"
  signal-cyan: "#38bdf8"
  ultraviolet: "#a855f7"
  heading-slate: "#cbd5e1"
  ambient-emerald: "rgba(52, 211, 153, 0.12)"
  card-surface: "rgba(255, 255, 255, 0.08)"
  card-surface-hover: "rgba(255, 255, 255, 0.14)"
  hairline: "rgba(255, 255, 255, 0.08)"
  hairline-soft: "rgba(255, 255, 255, 0.06)"
  icon-tint-bg: "rgba(56, 189, 248, 0.14)"
  icon-tint-text: "#e0f2fe"
typography:
  headline:
    fontFamily: "Inter, system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif"
    fontSize: "clamp(1.5rem, 3vw, 1.875rem)"
    fontWeight: 800
    lineHeight: 1.2
  title:
    fontFamily: "Inter, system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif"
    fontSize: "15px"
    fontWeight: 700
    lineHeight: 1.3
  section-label:
    fontFamily: "Inter, system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif"
    fontSize: "18px"
    fontWeight: 400
    letterSpacing: "0.08em"
  body:
    fontFamily: "Inter, system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif"
    fontSize: "15px"
    fontWeight: 400
    lineHeight: 1.6
  caption:
    fontFamily: "Inter, system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif"
    fontSize: "13px"
    fontWeight: 400
rounded:
  icon-badge: "12px"
  card: "14px"
  avatar: "22px"
  panel: "24px"
  full: "50%"
spacing:
  xs: "4px"
  sm: "12px"
  md: "20px"
  lg: "28px"
  xl: "32px"
components:
  link-card:
    backgroundColor: "{colors.card-surface}"
    textColor: "{colors.ink}"
    rounded: "{rounded.card}"
    padding: "14px 14px"
  link-card-hover:
    backgroundColor: "{colors.card-surface-hover}"
  link-icon:
    backgroundColor: "{colors.icon-tint-bg}"
    textColor: "{colors.icon-tint-text}"
    rounded: "{rounded.icon-badge}"
    size: "38px"
  avatar:
    rounded: "{rounded.avatar}"
    size: "80px"
---

# Design System: Brad Lumley

## Overview

**Creative North Star: "The Late-Night Console"**

One frosted-glass panel floats in the dark over a soft three-color ambient wash — a quiet instrument panel rather than a marketing surface. Chrome is minimal on purpose: a headshot, a title line, two labeled groups of link-tiles, and nothing else competing for attention. The page is calm and professional without reading as corporate — there's no stock photography, no illustration, no hero imagery beyond the real headshot; typography, spacing, and a single restrained accent color do all the work of establishing credibility.

Depth and color are both rationed. Sky-blue is the only hue allowed to signal interactivity; violet and a third emerald hue exist purely in the ambient background glow and are never asked to do UI work. Elevation follows the same discipline — the panel casts one soft ambient shadow at rest, and every card underneath it stays flat until a visitor actually hovers it.

**Key Characteristics:**
- Single frosted-glass panel afloat over a three-color ambient wash (cyan, violet, emerald)
- Sky-blue (`#38bdf8`) is the only color that signals interactivity; violet and emerald are ambient-only
- Zero imagery beyond the real headshot avatar — no illustration, no stock photography
- Flat at rest, lifted only on hover — depth is earned by interaction, not applied by default

## Colors

A near-black navy base lit by a restrained duo of glow colors, plus one ambient-only third hue that never touches an interactive surface.

### Primary
- **Signal Cyan** (`#38bdf8`): the only interactive accent — link-card hover border and glow, icon-badge tint, top-left corner of the ambient background wash.

### Secondary
- **Ultraviolet** (`#a855f7`): ambient-only. Appears in the top-right ambient wash and as the gradient partner in the section-header status dot. Never used on a clickable element.

### Tertiary
- **Ambient Emerald** (`rgba(52, 211, 153, 0.12)`): the third ambient-background wash (bottom-center), purely decorative depth — not a UI color and not reused anywhere else.

### Neutral
- **Midnight** (`#0f172a`): page background base, beneath the ambient gradients.
- **Card Surface** / **Card Surface Hover** (`rgba(255,255,255,0.08)` / `rgba(255,255,255,0.14)`): the glass panel's link-card background at rest and on hover/focus.
- **Ink** (`#e2e8f0`): primary text color (headline, link-card content).
- **Slate Muted** (`#94a3b8`): secondary/meta text — intro copy, link-card captions, footer.
- **Heading Slate** (`#cbd5e1`): section-label text ("Professional", "Lab").
- **Hairline** / **Hairline Soft** (`rgba(255,255,255,0.08)` / `rgba(255,255,255,0.06)`): the panel's outer border and each link-card's border, respectively.

### Named Rules
**The One Accent Rule.** Sky-blue is the only color allowed to signal interactivity — hover, focus, and icon tint all route through it. Violet and emerald are ambient-background colors only and never appear on a clickable element.

**Known defect, not a pattern to copy:** Slate Muted (`#94a3b8`) on the card surface measures ~3.8:1 contrast — below the WCAG AA 4.5:1 minimum that PRODUCT.md now requires for this site. Treat this as an open fix (see `/impeccable audit` or `/impeccable typeset`), not as an acceptable muted-text value for new work.

## Typography

**Body/Display Font:** Inter (with system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif fallback)

**Character:** One typeface carries the entire page. Inter's geometric neutrality reads as calm and technical rather than expressive — hierarchy comes entirely from size, weight, color, and letter-spacing, never from a second font.

### Hierarchy
- **Headline** (800, `clamp(24px, 3vw, 30px)`, line-height 1.2): the page name, appearing once in the header.
- **Section Label** (400, 18px, letter-spacing 0.08em, uppercase, color Heading Slate): "Professional" / "Lab" group titles, always paired with the gradient status dot.
- **Title** (700, 15px): each link-card's bolded name.
- **Body** (400, 15px, line-height 1.6, color Slate Muted): the intro sentence and link-card descriptions.
- **Caption** (400, 13px, color Slate Muted): the footer line; shares size with link-card secondary text.

### Named Rules
**The Loaded-Weight Rule.** Only request font weights actually fetched from Google Fonts (`400;600;700`). The header's declared weight of 800 falls outside that set and silently resolves to the nearest loaded weight (700) in-browser — either load 800 explicitly or drop the declared weight to 700 rather than leaving a weight that quietly does nothing.

## Layout

A single centered column: the body is a flex container centering one panel at `min(960px, 100%)` width, with 40px/16px/64px outer page padding (top/sides/bottom) on desktop. The panel's own internal padding steps down from 32px to 24px under 560px. Content never goes multi-column at the page level — the two link groups use an auto-fit grid (`repeat(auto-fit, minmax(220px, 1fr))`, 12px gap) that reflows on its own as the viewport narrows, with no dedicated breakpoint needed for the grid itself. One explicit breakpoint at 560px switches the header from a horizontal (avatar + text) row to a stacked column and shrinks the avatar from 80px to 72px.

Vertical rhythm: 24px between header and intro, 28px between sections, 16px between a section's label and its grid, 32px before the footer.

## Elevation & Depth

Glass-lifted: one resting elevation, everything else earned by interaction. The main panel sits on a soft, diffuse ambient shadow with an 8px backdrop blur against the gradient behind it — that's the system's only shadow at rest. Individual link-cards are flat until hovered; hovering adds a 2px lift, a cyan-tinted glow shadow, and a border-color shift, all in one 160ms transition.

### Shadow Vocabulary
- **Panel Ambient** (`box-shadow: 0 18px 40px rgba(0, 0, 0, 0.3)`): the resting shadow beneath the main glass panel.
- **Card Hover Glow** (`box-shadow: 0 10px 30px rgba(56, 189, 248, 0.15)`): appears only on a link-card's `:hover`/`:focus-visible`.

### Named Rules
**The Hover-Earns-Depth Rule.** No card casts a shadow at rest. Elevation is a response to interaction, never a static decoration.

## Shapes

Rounded rectangles throughout, with radius scaling to the element's size: 24px for the panel, 22px for the avatar (a rounded square, not a circle), 14px for link-cards, 12px for icon badges, and one true circle (50%) for the tiny gradient status dot beside each section label. Borders are limited to 1px hairlines; there are no hard corners anywhere in the system.

## Components

### Link Cards (signature component)
- **Shape:** 14px radius, 1px hairline border (`rgba(255, 255, 255, 0.06)`)
- **Background:** Card Surface at rest → Card Surface Hover on hover/focus
- **Hover/Focus:** `translateY(-2px)`, border tints to `rgba(56, 189, 248, 0.5)`, Card Hover Glow shadow appears; 160ms ease transition on transform/background/border-color/shadow
- **Disabled:** `aria-disabled="true"` variant drops opacity to 0.6 and fully suppresses hover/focus treatment — used for the "Nothing shipped yet" Lab placeholder
- **Internal layout:** icon badge + two-line text (Title above Caption), flex row, 12px gap, 14px padding

### Icon Badges
- **Style:** 38px square, 12px radius, Icon Tint Bg background, centered glyph (emoji or two-letter mark) in Icon Tint Text
- **State:** none of its own — inherits whatever state the parent link-card is in

### Avatar
- **Style:** 80px square (72px on mobile), 22px radius, `object-fit: cover`
- **Constraint:** always the real headshot — never a placeholder or initials avatar (binding, see PRODUCT.md Brand Commitments)

### Section Header
- **Style:** uppercase Section Label in Heading Slate, preceded by a 10px circular dot filled with a cyan→violet gradient and a soft cyan ring (`box-shadow: 0 0 0 6px rgba(56, 189, 248, 0.12)`)
- **Usage:** one per group ("Professional", "Lab") — the only place Ultraviolet appears outside the ambient background

## Do's and Don'ts

### Do:
- **Do** keep Signal Cyan as the only color that signals interactivity — hover, focus, and icon tint all route through it.
- **Do** keep the main panel's ambient shadow + blur as the system's single resting shadow; everything else stays flat until hovered.
- **Do** scale corner radius with element size (24px panel → 14px card → 12px badge) rather than picking one radius for everything.
- **Do** require a real photo for the avatar/OG/favicon set — no placeholder or initials avatar.

### Don't:
- **Don't** put violet or emerald on an interactive element — they're ambient-only and the section-header dot; giving them a hover/focus role breaks the One Accent Rule.
- **Don't** add a shadow to a card at rest — depth here is earned by interaction, not applied by default.
- **Don't** declare a font-weight Google Fonts hasn't loaded (only 400/600/700 are fetched) — the header's 800 declaration already does this silently; fix it rather than compounding it elsewhere.
- **Don't** ship muted text below 4.5:1 contrast — the current Slate Muted value measures ~3.8:1 on the card surface, which fails the WCAG AA bar PRODUCT.md now requires. It's a defect to fix, not a value to reuse.
