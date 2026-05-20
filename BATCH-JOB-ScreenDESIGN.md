# Design System Strategy: The Curated Workspace

## 1. Overview & Creative North Star
The Creative North Star for this design system is **"The Digital Atelier."** 

In enterprise software, density often leads to clutter. This system rejects the "spreadsheet" aesthetic in favor of a high-end, editorial dashboard experience. We move beyond the standard SaaS template by treating the interface as a curated workspace. We achieve this through **Intentional Asymmetry**—where large, bold Manrope display type anchors the page, balanced by generous whitespace and layered "frosted" surfaces. This is not just a dashboard; it is a professional environment designed for focus, authority, and clarity.

## 2. Colors & Surface Philosophy
The palette is rooted in a deep, authoritative Indigo, balanced by a sophisticated Tertiary Orange to draw the eye to high-value actions.

### The "No-Line" Rule
To achieve a premium feel, **1px solid borders are prohibited for sectioning.** We do not use lines to cage data. Instead, boundaries are defined strictly through background color shifts.
*   **Workspace:** Use `surface` (#f8f9fa).
*   **Primary Containers:** Use `surface_container_low` (#f3f4f5) to create distinct regions without visual noise.
*   **Interactive Cards:** Use `surface_container_lowest` (#ffffff) to make data "pop" against the workspace.

### Surface Hierarchy & Nesting
Think of the UI as physical layers of fine paper. 
*   **Base:** `background` (#f8f9fa).
*   **Sectioning:** `surface_container` (#edeeef).
*   **Emphasis:** To highlight a specific module within a section, use `surface_container_highest` (#e1e3e4). This nesting creates depth through value rather than structure.

### The Glass & Gradient Rule
For floating elements (modals, dropdowns, or hovering action bars), use **Glassmorphism**. Apply `surface_container_lowest` at 80% opacity with a `backdrop-filter: blur(12px)`. 
*   **Signature Textures:** Primary CTAs should not be flat. Use a subtle linear gradient from `primary` (#3525cd) to `primary_container` (#4f46e5) at a 135-degree angle to give buttons a tactile, high-end "pressable" quality.

## 3. Typography
We utilize a dual-font pairing to balance professional rigor with editorial flair.

*   **Display & Headlines (Manrope):** Used for data storytelling. Large `display-lg` (3.5rem) or `headline-md` (1.75rem) type should be used to anchor the page, creating a clear entry point for the user’s eye.
*   **Interface & Body (Inter):** Used for utility. Inter provides maximum legibility at smaller scales. Use `body-md` (0.875rem) for the majority of data points to maintain a clean, professional density.
*   **Hierarchy as Identity:** By using a significant scale jump between `headline-lg` and `body-md`, we create an "Editorial Hierarchy" that makes the dashboard feel like a high-end report rather than a generic tool.

## 4. Elevation & Depth
Traditional drop shadows are often "muddy." This system uses **Tonal Layering** and **Ambient Light**.

*   **The Layering Principle:** Place a `surface_container_lowest` card on a `surface_container_low` background. The contrast in hex value provides enough "lift" for 90% of use cases.
*   **Ambient Shadows:** When a shadow is required (e.g., for a floating modal), use a diffused shadow: `box-shadow: 0 12px 32px rgba(25, 28, 29, 0.06)`. Note the use of the `on_surface` color tinted at 6%—this mimics natural light better than pure black.
*   **The Ghost Border Fallback:** If a container sits on a background of the same color, use a "Ghost Border": `outline_variant` (#c7c4d8) at 15% opacity. Never use 100% opaque borders.

## 5. Components

### Buttons
*   **Primary (Indigo):** Gradient of `primary` to `primary_container`. Corner radius: `md` (0.75rem).
*   **Accent (Orange):** Use `tertiary_container` (#a04500) with `on_tertiary` text for "Save" or "Submit" actions to provide a warm, urgent contrast to the cool Indigo.
*   **Tertiary:** Ghost style. No background, `on_surface_variant` text, `sm` (0.25rem) radius on hover.

### Forms & Inputs
*   **Structure:** Inputs must use `surface_container_lowest` with a "Ghost Border" of `outline_variant` at 20%. 
*   **Focus State:** Transition the border to `primary` (#3525cd) and add a subtle 2px outer glow using `primary_fixed_dim`.
*   **Clarity:** Labels use `label-md` (Inter, 0.75rem) in `on_surface_variant` for a muted, professional look.

### Cards & Lists
*   **The Divider Ban:** Do not use line dividers between list items. Use `spacing-4` (1rem) of vertical whitespace and a subtle background hover state change to `surface_container_high`.
*   **Data Chips:** Use `secondary_fixed` (#e1e0ff) with `on_secondary_fixed_variant` (#2f2ebe) text. Shape: `full` (9999px) for a soft, pill-like aesthetic.

### Additional Signature Components
*   **The Key Metric Block:** A high-contrast card using `primary_container` as the background with `on_primary_container` text to highlight the "North Star" metric of the dashboard.
*   **Contextual Tooltips:** Small, high-contrast dark tooltips using `inverse_surface` with `inverse_on_surface` text, appearing with a 200ms ease-out fade.

## 6. Do’s and Don’ts

### Do
*   **Do** use `lg` (1rem) corner radius for main dashboard modules to create a "soft" enterprise feel.
*   **Do** lean into `spacing-8` (2rem) and `spacing-10` (2.5rem) between major sections to let the data breathe.
*   **Do** use `tertiary` (Orange) sparingly—only for final confirmation or high-alert status.

### Don’t
*   **Don’t** use pure black (#000000) for text. Always use `on_surface` (#191c1d) for better readability.
*   **Don’t** use 1px lines to separate sidebar from main content; use a background shift from `surface_container_low` to `surface`.
*   **Don’t** overcrowd a single view. If a screen requires more than 6 widgets, use a tabbed interface or progressive disclosure.