# Design System Strategy: Kinetic Monolith (Rossilber Edition)

## 1. Overview & Creative North Star
The Creative North Star for this design system is **"The Kinetic Monolith."** 

This isn't a standard corporate dashboard; it is a high-performance environment designed to feel solid, authoritative, and fast. Inspired by the brutalist aesthetics of heavy industry and the precision of aerospace telemetry, the system breaks away from "template" looks by utilizing hard edges (0px border radius), massive typographic scales, and intentional asymmetry. We treat the screen not as a page, but as a dense, backlit command center. 

By replacing traditional blue corporate accents with the high-energy Red (`primary`) and Orange (`secondary`) extracted from the Rossilber identity, we create a high-contrast, aggressive performance aesthetic that demands attention against deep, obsidian backgrounds.

---

## 2. Colors
Our palette is rooted in deep blacks and tactical grays, allowing the brand’s "kinetic" colors to serve as heat maps for user action.

### The "No-Line" Rule
**Explicit Instruction:** Sectioning via 1px solid borders is strictly prohibited. We define boundaries through volume and light, not lines. 
- Use background color shifts (e.g., a `surface-container-low` section sitting on a `surface` background) to denote change in context.
- High-performance interfaces should feel seamless and carved from a single block of material.

### Surface Hierarchy & Nesting
Treat the UI as a series of nested, physical layers. 
- **Base:** `surface` (#131313) or `surface-container-lowest` (#0e0e0e) for the core canvas.
- **Elevation:** Use `surface-container` (#201f1f) through `surface-container-highest` (#353534) to "lift" important modules. 
- **The Glass & Gradient Rule:** For floating elements or top-level navigation, use semi-transparent surface colors with a `backdrop-blur` (Glassmorphism). To provide "visual soul," apply subtle linear gradients transitioning from `primary` (#ffb4ac) to `primary_container` (#e21f26) on main CTAs to mimic the light-catch on polished industrial metal.

---

## 3. Typography
We use **Inter** exclusively to maintain a sharp, technical, and professional atmosphere. The hierarchy is designed for rapid information processing.

- **Display Scales (`display-lg` to `display-sm`):** These are the "Monolith" headers. Use these sparingly for hero numbers or high-level category titles. They should feel massive and immovable.
- **Headline & Title Scales:** Designed for immediate legibility. The contrast between `headline-lg` (2rem) and `body-md` (0.875rem) creates an editorial tension that keeps the interface from looking like a generic grid.
- **The Functional Layer:** `label-md` and `label-sm` are your telemetry fonts. Use these for metadata, status indicators, and small-caps technical data points.

---

## 4. Elevation & Depth
In this design system, depth is achieved through **Tonal Layering** rather than drop shadows.

- **The Layering Principle:** Stacking tiers (e.g., a `surface-container-high` card on a `surface-container-low` background) provides a soft, natural lift.
- **Ambient Shadows:** Shadows are a fallback, not a feature. If a "floating" effect is mandatory, use an extra-diffused shadow with 4% opacity, using a tinted version of `on-surface` (#e5e2e1) to mimic natural ambient occlusion.
- **The "Ghost Border":** If accessibility requires a container edge, use the `outline_variant` (#5d3f3c) at **20% opacity**. This creates a "glint" on the edge of the monolith rather than a heavy outline.
- **Backdrop Blur:** Floating navigation bars must use `surface` at 80% opacity with a 20px blur to allow the brand-colored "kinetic" content to bleed through as the user scrolls.

---

## 5. Components

### Buttons
- **Primary:** Background: Gradient `primary` to `primary_container`. Text: `on_primary_fixed` (#410003). 0px border radius.
- **Secondary:** Background: `secondary_container` (#ef7c00). Text: `on_secondary_fixed` (#301400).
- **Tertiary:** No background. Text: `primary`. Subtle hover state using `surface_bright`.

### Input Fields
- Avoid boxed inputs. Use a bottom-only "Ghost Border" or a `surface_container_highest` background with 0px rounding. 
- Error states must use the high-visibility `error` (#ffb4ab) color for both the border-bottom and the helper text.

### Cards & Lists
- **Rule:** Forbid the use of divider lines. 
- Use the **Spacing Scale** (e.g., `8` or `10`) to create "Active Negative Space." 
- For list items, use a subtle background hover shift to `surface_container_high`.

### Telemetry Chips
- Small, rectangular (0px radius) chips using `tertiary_container` for background and `on_tertiary_container` for text. These should look like labels on an industrial control panel.

---

## 6. Do's and Don'ts

### Do:
- **Do** use `secondary` (Orange) for secondary actions or "Warning" level telemetry to contrast with the `primary` (Red).
- **Do** embrace 0px roundedness across all elements to reinforce the "Monolith" aesthetic.
- **Do** use extreme vertical whitespace (Spacing 16-24) to separate major content blocks.

### Don't:
- **Don't** use blue accents. The transition to the Rossilber Red/Orange palette must be absolute.
- **Don't** use standard 1px #000 dividers. They clutter the technical precision of the dark interface.
- **Don't** use rounded corners (`lg`, `md`, `sm`). If a component library defaults to 4px, manually override to **0px**.
- **Don't** use pure white (#FFFFFF) for body text. Use `on_surface` (#e5e2e1) to reduce eye strain in high-performance dark environments.