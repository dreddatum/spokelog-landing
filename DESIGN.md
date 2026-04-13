# Design System Document: Industrial Authority

## 1. Overview & Creative North Star: "The Blueprint Monolith"
The construction industry is built on precision, heavy-duty reliability, and structural integrity. This design system moves away from the "flimsy" feel of generic SaaS platforms to embrace **The Blueprint Monolith**. 

This Creative North Star focuses on a digital experience that feels as solid as a structural beam. We achieve this through intentional asymmetry (mimicking site plans), massive typographic scales that demand attention, and a "Material-Honesty" approach—where depth is created through tonal stacking rather than artificial decorative elements. We are replacing the "web template" look with an editorial, high-end technical manual aesthetic.

---

## 2. Colors: Tonal Rigidity
Our palette reflects the job site: concrete, steel, and the high-visibility "Construction Blue."

### The "No-Line" Rule
**Strict Mandate:** Designers are prohibited from using 1px solid borders to section off content. In this system, boundaries are defined by "The Pour." Just as concrete is poured into forms, our content is defined by shifts in background tokens. Use `surface-container-low` against a `surface` background to create a section. 

### Surface Hierarchy & Nesting
Treat the UI as a physical assembly.
*   **Base Layer:** `surface` (#f7f9fc) – The "site" foundation.
*   **Secondary Zones:** `surface-container-low` (#f2f4f7) – Used for large sidebar or grouping areas.
*   **Interactive Containers:** `surface-container-lowest` (#ffffff) – Reserved for the most important cards or data entry fields to make them "pop" forward.

### Signature Textures & The "Glass" Rule
To prevent the UI from feeling "flat" or "cheap," use a subtle linear gradient on primary CTAs: `primary-container` (#0047ab) transitioning 15% toward `primary` (#00327d) at a 135-degree angle. This mimics the slight sheen of finished steel. For floating utility panels (e.g., toolbars), use **Glassmorphism**: `surface_container_lowest` at 80% opacity with a 16px backdrop blur to maintain the "monolith" feel while showing the data beneath.

---

## 3. Typography: The Engineering Spec
We use **Inter** exclusively for its neutral, technical clarity. The hierarchy is designed to feel like an architectural drawing—authoritative and impossible to ignore.

*   **Display (lg/md/sm):** Used for "Hero" stats or project titles. These should always be `font-weight: 800` (Extra Bold) with a slight tracking decrease (-0.02em) to feel "heavy."
*   **Headlines:** These are your "Structural Ribs." Use `headline-lg` for section headers. They provide the rhythm of the page.
*   **Titles:** Used for card headers. Bold and concise.
*   **Body:** `body-lg` is the default for readability. For technical specs or "fine print" data, use `body-sm`.
*   **Labels:** `label-md` and `label-sm` should be uppercase with +0.05em letter spacing to mimic industrial labeling and blueprint annotations.

---

## 4. Elevation & Depth: Tonal Layering
In this system, we do not "drop shadows"; we "layer mass."

*   **The Layering Principle:** Depth is achieved by stacking. A `surface-container-lowest` card placed on a `surface-container` background creates a natural, sharp lift.
*   **Ambient Shadows:** If a component must float (e.g., a Modal), use a custom shadow: `0px 20px 40px rgba(25, 28, 30, 0.06)`. The shadow color is derived from `on-surface` (#191c1e), making it feel like an ambient occlusion shadow on a construction site, not a digital glow.
*   **The "Ghost Border" Fallback:** If accessibility requires a stroke (e.g., in high-contrast situations), use `outline-variant` (#c3c6d5) at 20% opacity. Never use 100% opaque lines.

---

## 5. Components: Structural Units

### Buttons (The "Actuators")
*   **Primary:** `primary-container` background, `on-primary` text. Solid, heavy, and rectangular (`DEFAULT` radius: 0.25rem). 
*   **Secondary:** `surface-container-high` background. No border. Text in `on-surface`.
*   **Tertiary:** Text-only in `primary-container`. Use for low-priority actions like "Cancel."

### Input Fields
*   Background: `surface-container-highest` (#e0e3e6).
*   Shape: 0.25rem radius.
*   Indicator: Instead of a full border, use a 2px bottom-accent of `primary` only when the field is focused.

### Cards & Lists
*   **Forbid Divider Lines:** Separate list items using 16px or 24px of vertical whitespace.
*   **The "Blueprint" Card:** Use `surface-container-lowest` with a "Ghost Border" (20% opacity `outline-variant`) to define the edge without cluttering the visual field.

### Industrial Progress Bars
Instead of rounded, "bubbly" bars, use sharp-edged bars with `primary` for the fill and `surface-container-highest` for the track. This looks like a measuring tape or gauge.

---

## 6. Do's and Don'ts

### Do:
*   **Use Intentional Asymmetry:** Align text to the left but allow large imagery or data visualizations to bleed off the right edge of the grid.
*   **Embrace Whitespace:** Construction sites are vast; your UI should be too. Use generous padding (32px+) between major sections.
*   **Use Tonal Shifts:** Always use `surface-container-low` for background "wells" to hold content.

### Don't:
*   **No Abstract Shapes:** Never use circles, blobs, or wavy lines. Every shape must be a rectangle or a right-angle polygon.
*   **No 100% Black:** Always use `on-surface` (#191c1e) for text. True black feels "digital" and "cheap"; our charcoal-tinted grey feels industrial.
*   **No "Floating" Elements:** Avoid placing white cards on white backgrounds with heavy shadows. Use the Tonal Layering principle instead.