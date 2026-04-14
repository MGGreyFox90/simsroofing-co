```markdown
# Design System Document: Architectural Integrity

## 1. Overview & Creative North Star: "The Structural Monolith"
The roofing industry is defined by protection, structural integrity, and enduring quality. This design system moves away from the "cluttered contractor" aesthetic toward **The Structural Monolith**. 

Our Creative North Star focuses on **Architectural Editorialism**. We treat the digital canvas like a blueprint—clean, precise, and authoritative. We break the standard template look by using intentional asymmetry (e.g., imagery breaking the container edge), overlapping typographic elements, and a high-contrast scale that commands attention. The goal is to make Sims Roofing feel less like a local service and more like an established architectural firm.

---

### 2. Colors: Tonal Depth & The "No-Line" Rule
We use color not just for branding, but to define space and hierarchy.

*   **Primary (`#002046`):** The "Deep Anchor." Used for heavy typographic moments and foundational sections to evoke trust and depth.
*   **Tertiary (`#381800` / `#f77d03`):** The "Safety Beacon." We use these burnt oranges and deep ambers sparingly—only for critical calls to action (CTAs) and directional cues.
*   **Secondary (`#4c616c`):** The "Slate Overlay." Bridges the gap between the dark primary and the light background.

#### The "No-Line" Rule
**Explicit Instruction:** Do not use 1px solid borders to section content. Boundaries must be defined through background color shifts.
*   A section using `surface-container-low` should sit directly against a `surface` background.
*   Use `surface-container-highest` for nested utility areas (like a sidebar) to create a natural, "carved-out" feel rather than a "boxed-in" one.

#### Glass & Gradient Rule
To provide "soul" to the UI, use subtle linear gradients. 
*   **Hero Backgrounds:** Transition from `primary` (`#002046`) to `primary_container` (`#1b365d`) at a 135-degree angle.
*   **Glassmorphism:** For floating navigation or modal overlays, use `surface` at 80% opacity with a `20px` backdrop-blur.

---

### 3. Typography: The Editorial Voice
Our typography pairing balances the "Work" (Work Sans) with the "Human" (Manrope).

*   **Display & Headlines (Work Sans):** Bold, masculine, and unapologetic. Use `display-lg` (3.5rem) for hero statements. Apply a slight negative letter-spacing (-0.02em) to headlines to increase the "heavy" professional feel.
*   **Body & Titles (Manrope):** Chosen for its modern, geometric clarity. Manrope provides a technical "blueprint" feel that complements the bold headlines.
*   **Hierarchy as Brand:** Use `label-md` in all-caps with increased letter-spacing (0.1em) for category tags (e.g., "RESIDENTIAL," "COMMERCIAL") to create an upscale architectural vibe.

---

### 4. Elevation & Depth: Tonal Layering
Traditional shadows and borders are replaced by **Tonal Layering**.

*   **The Layering Principle:** Depth is achieved by stacking tiers. Place a `surface-container-lowest` card on a `surface-container-low` section. This creates a "soft lift" that feels like high-end stationery.
*   **Ambient Shadows:** If a card must "float" (e.g., a featured testimonial), use a shadow with a blur of `40px`, a Y-offset of `12px`, and an opacity of `6%` using the `on-surface` color. It should feel like a soft glow, not a hard drop.
*   **The "Ghost Border" Fallback:** For input fields where a boundary is required, use `outline-variant` at **15% opacity**. High-contrast borders are strictly forbidden as they interrupt the visual flow.

---

### 5. Components: Precision & Utility

#### Service Cards
*   **Structure:** No borders. Use `surface-container-low`. 
*   **Hover State:** Transition to `surface-container-highest` with a slight upward translation (-4px).
*   **Content:** Large `title-lg` headers. Icons should be monochrome using `on-secondary-container`.

#### The "Sims" Contact Form
*   **Inputs:** Large, breathable fields using `surface-container-highest`. Labels should use `label-md` positioned above the field.
*   **CTA:** Primary Button using `primary` background. To add a premium touch, apply a subtle inner-glow (1px white at 10% opacity) to the top edge to simulate a physical button.

#### Testimonial Sections
*   **Layout:** Overlap a high-resolution project image with a `surface-container-lowest` text card.
*   **Typography:** Use `headline-sm` for the quote to give the customer's voice authority.

#### Buttons
*   **Primary:** `primary` background, `on-primary` text. `0.25rem` (DEFAULT) roundedness for a sharp, professional corner.
*   **Secondary:** `secondary-container` background. Use for "Learn More" or "View Gallery."
*   **Tertiary:** No background. Bold `label-md` with an `on-tertiary-container` underline that expands on hover.

---

### 6. Do's and Don'ts

#### Do
*   **DO** use whitespace as a structural element. If you think it needs more space, double it.
*   **DO** use "Sims Orange" (`on-tertiary-container`) for text links within body copy to ensure visibility.
*   **DO** ensure imagery is high-contrast, architectural, and clean (avoiding cluttered job-site photos).

#### Don't
*   **DON'T** use `primary` for every background; the "Deep Anchor" loses its power if used everywhere.
*   **DON'T** use standard 1px dividers between list items. Use 24px–32px of vertical padding to separate items.
*   **DON'T** use fully rounded (pill) buttons. The system relies on the `0.25rem` (sm) or `0.5rem` (lg) radius to maintain a "built" and "constructed" aesthetic.

---

### 7. Implementation Note: The Asymmetric Grid
When building pages, avoid the "center-everything" trap. Place headline text on the left-third of the grid, and allow images to bleed off the right edge of the screen. This "breaking of the box" is what transforms a standard roofing site into a high-end digital experience.