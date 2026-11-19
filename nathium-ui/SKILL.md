---
name: nathium-ui
description: Avoid generic AI "vibe-code" purple/neon defaults and build clean, intentional user interfaces. Use when designing UI/UX, generating frontend HTML/CSS/React code, styling Tailwind/shadcn interfaces, or auditing visual hierarchy, color contrast, spacing, border radii, icons, and micro-interactions.
---
# Nathium UI

Design and build clean, intentional, high-craft user interfaces by eliminating generic AI-generated defaults and applying strict visual, spatial, and motion principles.

## When to Use

- Building or styling web applications, dashboards, landing pages, or UI components
- Writing frontend HTML/CSS, Tailwind CSS, shadcn/ui, or React interfaces
- Reviewing, auditing, or refactoring existing UI code for better visual hierarchy, color harmony, and polish

## Core UI Principles

### 1. Color & Contrast Discipline

- **Eliminate "Vibe-Code" Colors:** Avoid default AI purple/magenta/neon gradients and oversaturated palettes. High saturation causes eye strain and reduces retention; aim for restrained, low-saturation palettes (unless explicitly building neo-brutalism).
- **Use HSL Intentionally:** Adjust Hue, Saturation, and Lightness systematically rather than picking arbitrary hex codes.
- **Calibrate for Dark Mode:** Colors appear brighter against dark backgrounds. Desaturate accents or adjust lightness on dark surfaces so colors do not vibrate or overwhelm the eye.
- **Prevent Halation:** Avoid pure black (`#000000`) on pure white (`#FFFFFF`) or vice versa, which creates a blurry optical glow. Use slightly tinted off-whites and soft charcoal/dark-gray surfaces instead.
- **Enforce WCAG Contrast:** Maintain strong text-to-background readability ratios (target WCAG AA minimum, AAA where practical for body copy).
- **Handle Shadows Properly:** Keep shadows neutral (never colored). In dark mode, rely on subtle borders and surface lightness shifts rather than drop shadows to convey elevation.

### 2. Layout, Spacing & Geometry

- **4px Grid System:** Use spacing values in multiples of 4px (`4px`, `8px`, `12px`, `16px`, `24px`, `32px`, `48px` - standard Tailwind/shadcn spacing units) for consistent rhythm and alignment.
- **Concentric Border Radii:** When nesting rounded elements, calculate the outer radius as `outer_radius = inner_radius + padding` (e.g., an inner `20px` element with `8px` padding sits inside a `28px` outer container) so corners curve concentrically.
- **Alternate Data Layouts:** Do not default to repetitive cards or plain tables for every dataset. Use matrix visualizations, dense telemetry grids, structured inline badges, or timeline/log views when they fit the data better.

### 3. Iconography

- **Consistent Style & Weight:** Never mix icon styles (such as outline, duotone, thin, and filled) within the same interface. Keep stroke weight and dimensions uniform across all icons.
- **Intentional Active States:** Differentiate focused or active icons by changing stroke color or switching to the filled variant of the exact same icon family.

### 4. Motion & Micro-Interactions

- **Natural Easings:** Avoid linear (`y = x`) transitions. Use purposeful easing curves (cubic, quartic, quintic, exponential, or subtle spring/back curves) to give motion physical weight.
- **Purposeful Micro-Interactions:** Add subtle hover states, state transitions, copy/extract feedback, and layout animations (inspired by tools like Linear, Notion, and Supabase) to make interfaces feel responsive and refined.

## Workflow

1. **Establish Palette & Tokens:** Define muted HSL surface, border, text, and single accent tokens first, verifying contrast and avoiding pure `#000000`/`#FFFFFF` pairs.
2. **Structure Hierarchy & Layout:** Choose the clearest layout for the content (avoiding unnecessary card wrappers) and enforce the 4px spacing scale.
3. **Refine Geometry & Icons:** Match nested `border-radius` values to container padding and lock in a single icon weight and family.
4. **Add Motion & Feedback:** Apply non-linear easing transitions and crisp hover/active states to interactive controls.

## Gotchas

- **Defaulting to Purple/Blue Gradients:** Always replace generic purple-pink hero gradients or glowing purple buttons with restrained neutral surfaces and a single purposeful accent.
- **Mismatched Nested Corners:** Using the exact same `border-radius` on both a parent card and an inner button/input creates awkward pinching; always add the padding to the outer radius.
- **Drop Shadows in Dark Mode:** Dark shadows disappear on dark backgrounds and colored shadows look muddy; use `1px` subtle borders and stepped surface lightness instead.
