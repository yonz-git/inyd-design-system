---
version: alpha
name: INYD
description: Dark editorial design system extracted from monopo.vn — grain-black canvas, oversized light-weight type, deep rose-gold gradient accents, pill ghost buttons.

colors:
  background: "#010101"
  on-background: "#FFFFFF"
  surface: "#181818"
  on-surface: "#FFFFFF"
  surface-inverse: "#FFFFFF"
  on-surface-inverse: "#010101"
  text-secondary: "#CBCBCB"
  text-tertiary: "#6D6D6D"
  border: "#4D4D4D"
  accent: "#FF8469"
  gradient-rose-deep: "#763A3D"
  gradient-rose: "#B27469"
  gradient-rose-gold: "#D9A392"
  success: "#A0E0AB"
  warning: "#FFAC2E"
  error: "#A52D25"
  info: "#458F51"

typography:
  marquee:
    fontFamily: Roobert, Manrope, system-ui, sans-serif
    fontSize: 224px
    fontWeight: 300
    lineHeight: 1.25
    letterSpacing: -0.02em
  display:
    fontFamily: Roobert, Manrope, system-ui, sans-serif
    fontSize: 78px
    fontWeight: 300
    lineHeight: 1.06
    letterSpacing: -0.01em
  h1:
    fontFamily: Roobert, Manrope, system-ui, sans-serif
    fontSize: 54px
    fontWeight: 300
    lineHeight: 1.4
  h2:
    fontFamily: Roobert, Manrope, system-ui, sans-serif
    fontSize: 37px
    fontWeight: 400
    lineHeight: 1.3
  h3:
    fontFamily: Roobert, Manrope, system-ui, sans-serif
    fontSize: 28px
    fontWeight: 300
    lineHeight: 1.4
  h4:
    fontFamily: Roobert, Manrope, system-ui, sans-serif
    fontSize: 18px
    fontWeight: 400
    lineHeight: 1.2
  body:
    fontFamily: Roobert, Manrope, system-ui, sans-serif
    fontSize: 15px
    fontWeight: 400
    lineHeight: 1.65
  body-small:
    fontFamily: Roobert, Manrope, system-ui, sans-serif
    fontSize: 12px
    fontWeight: 300
    lineHeight: 1.6
  label:
    fontFamily: Roobert, Manrope, system-ui, sans-serif
    fontSize: 11px
    fontWeight: 600
    lineHeight: 1.2
    letterSpacing: 0.04em
    fontFeature: uppercase
  nav:
    fontFamily: Roobert, Manrope, system-ui, sans-serif
    fontSize: 13px
    fontWeight: 300
    lineHeight: 1.2
    letterSpacing: 0.28em
    fontFeature: uppercase
  mono:
    fontFamily: ui-monospace, SFMono-Regular, Menlo, monospace
    fontSize: 13px
    fontWeight: 400
    lineHeight: 1.5

rounded:
  none: 0px
  sm: 10px
  pill: 999px

spacing:
  xs: 8px
  sm: 16px
  md: 24px
  lg: 40px
  xl: 64px
  2xl: 96px
  3xl: 160px

components:
  button-ghost:
    textColor: "{colors.on-background}"
    typography: "{typography.body-small}"
    rounded: "{rounded.pill}"
    padding: 19px 40px
  button-ghost-hover:
    backgroundColor: "{colors.gradient-rose}"
    textColor: "{colors.on-background}"
    typography: "{typography.body-small}"
    rounded: "{rounded.pill}"
    padding: 19px 40px
  button-solid:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.on-surface}"
    typography: "{typography.body-small}"
    rounded: "{rounded.pill}"
    padding: 19px 48px
  chip-label:
    textColor: "{colors.text-secondary}"
    typography: "{typography.label}"
    rounded: "{rounded.none}"
    padding: 0px
  nav-link:
    textColor: "{colors.on-background}"
    typography: "{typography.nav}"
    rounded: "{rounded.none}"
    padding: 8px 0px
  card-project:
    backgroundColor: "{colors.background}"
    textColor: "{colors.on-background}"
    typography: "{typography.h4}"
    rounded: "{rounded.none}"
    padding: 0px
  footer-link:
    textColor: "{colors.on-background}"
    typography: "{typography.h2}"
    rounded: "{rounded.none}"
    padding: 0px
---

# INYD Design System

## Overview

INYD adopts the visual language of monopo saigon (monopo.vn): a Tokyo-born creative-studio aesthetic that reads as cinematic, editorial, and quietly confident. The system lives on a grain-textured near-black canvas where oversized, light-weight typography does almost all of the work, punctuated by a single coral accent and its sunset gradient. It should feel like a title sequence, not a dashboard. Anti-patterns to guard against: it must never become a colorful, rounded "SaaS-friendly" UI, and it must never get dense — if a screen feels busy, remove elements rather than shrinking them.

## Colors

The palette is radically restrained: `background` (#010101, a hair off pure black so the grain texture reads) carries `on-background` white text; `surface` (#181818) is the only elevation step, used for filled buttons and hover states. The signature gradient is a deep rose gold — `gradient-rose-deep` (#763A3D) rising through `gradient-rose-gold` (#D9A392) and settling into `gradient-rose` (#B27469), rendered at ~115° with a soft, grainy blend — and it appears only on interaction: hover fills, link underlines, progress. Never as static decoration. Coral (`accent`, #FF8469) is the gradient's bright cousin, reserved for tiny static highlights and marks. Long editorial passages step down through `text-secondary` (#CBCBCB) and `text-tertiary` (#6D6D6D); `border` (#4D4D4D) is the rendered equivalent of the site's 30%-white hairlines on black. The system also flips whole sections to an inverse mode: `surface-inverse` white with `on-surface-inverse` near-black text, mirroring the palette exactly. Semantic colors (`success`, `warning`, `error`, `info`) are muted pastels/darks used sparingly; `error` (#A52D25) is too dark for text on black — use it as a fill with white text. White on #010101 passes WCAG AAA; `text-tertiary` is for non-essential meta only.

## Typography

One family everywhere: Roobert, a geometric grotesque whose slightly quirky terminals keep the minimalism from feeling sterile (Manrope is the free fallback; the original site pairs it with Raleway for Vietnamese diacritics). The voice of the system is the Light (300) weight at enormous sizes — `display` (78px) for section statements and `marquee` (224px) for scrolling set-pieces — set tight (line-height 1.06, tracking −1%). Against that, `label` and `nav` are tiny uppercase utilities (11–13px) with open tracking; the tension between huge-and-light and tiny-and-tracked *is* the brand. `body` is small by contemporary standards (15px) with a generous 1.65 line-height for an editorial column feel. Weight 600 appears only at label size; never bold a headline — scale up instead. Sizes are desktop-reference values (1440px viewport): implement them fluidly (vw or clamp()) so display type keeps its proportion of the screen.

## Layout

Spacing follows a base-8 scale from `xs` (8px) to `3xl` (160px), and the system leans hard on the top end: sections breathe with `2xl`–`3xl` vertical padding, and a screen typically contains one idea at a time. Content sits in a full-bleed container with generous side margins (~5vw); media runs edge-to-edge. There is no visible grid — compositions are asymmetric, with type blocks offset against imagery and deliberate empty zones. Density is "generous" to the point of luxury: when in doubt, double the space.

## Elevation & Depth

Completely flat — no box shadows anywhere in the system. Depth is communicated three ways: contrast steps (`background` → `surface` → white media), 1px hairline borders (`border`), and layering of oversized type over imagery. The original site adds a live film-grain texture over the black canvas, which gives the flatness a physical, analog quality; a subtle noise overlay (2–4% opacity) is the sanctioned substitute. Never introduce drop shadows or glassmorphism blurs; they break the print-like flatness.

## Shapes

Two shape languages coexist with strict roles. Interactive pills: buttons and clickable tags use `rounded.pill` (fully rounded), always paired with a 1px hairline border when unfilled — the pill silhouette is the system's only "soft" element and therefore reads unmistakably as *pressable*. Everything else is sharp: cards, images, video frames, and containers use `rounded.none`, keeping the editorial, printed feel. `rounded.sm` (10px) exists only for small utility surfaces (toasts, cookie banners, embedded players). Avatars and dot cursors may be full circles.

## Components

`button-ghost` is the primary CTA: transparent with a 1px `border` hairline, pill-shaped, small tracked-uppercase text — on hover it becomes `button-ghost-hover`, filling with the rose-gold gradient (deep rose → rose gold → rose, ~115°; the flat `gradient-rose` token is the non-gradient fallback) while text stays white for contrast against the deep end. `button-solid` (#181818 fill) is the secondary, used on media or white sections. `chip-label` renders project/category metadata as bare uppercase micro-text — no boxes, no backgrounds. `nav-link` is tracked uppercase; its active/hover state is a 1px underline or an opacity shift from 0.6 to 1, never a color change. `card-project` is a sharp-cornered image block with `h4` title and `chip-label` meta below; hover scales the image ~1.05 inside a clipped frame and reveals nothing new — motion is the feedback. `footer-link` sets contact actions (email, socials) at `h2` scale, treating navigation itself as display typography. Disabled states drop to 30% opacity across all components.

## Do's and Don'ts

**Do:**
- Let one oversized Light-weight headline dominate each screen; scale type up rather than adding elements.
- Reserve the rose-gold gradient (deep rose → rose gold) for interaction feedback — hovers, active states, progress.
- Use uppercase 11px labels with open tracking for every piece of meta text (categories, roles, dates).
- Keep media and cards sharp-cornered and edge-to-edge; keep pills exclusively for pressable things.
- Animate with slow, eased reveals (opacity + translate) — the brand moves like film, not like an app.
- Maintain the two-mode symmetry: any section may invert to white, swapping the palette exactly.

**Don't:**
- Don't bold headlines or use weights above 400 at sizes over 15px — weight 600 lives at label size only.
- Don't introduce box shadows, glows, or glass blur; depth comes from contrast and hairlines.
- Don't use the coral accent as static decoration, large fills, or body-text color.
- Don't round the corners of cards, images, or containers — pill radius means "interactive" and nothing else.
- Don't tighten spacing to fit more content; cut content instead.
- Don't add new hues — the palette is black, white, two grays, the three rose-gold gradient stops, and the coral accent.
