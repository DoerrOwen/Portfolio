```markdown
# Design System Strategy: The Experimental Gallery

## 1. Overview & Creative North Star
The Creative North Star for this design system is **"The Digital Curator."** 

This system moves away from the rigid, utility-first structures of standard enterprise software and instead adopts the persona of a high-end, contemporary art gallery. It treats the screen as a physical space where technical precision (Google’s engineering DNA) meets avant-garde creative flair (the Fellowship’s soul). 

The experience is defined by **Intentional Asymmetry** and **Breathing Room**. We do not fill the screen; we curate it. By utilizing massive scale shifts in typography and a "layered paper" approach to depth, we create a UI that feels less like a website and more like an interactive installation.

---

## 2. Colors & The Surface Manifesto
The palette utilizes a clinical white base (`surface`) to allow Google’s primary brand colors to function as light-sources and interactive "signals."

### The "No-Line" Rule
**Explicit Instruction:** Traditional 1px solid borders are strictly prohibited for sectioning. Boundaries must be defined solely through background color shifts or the use of `surface-container` tiers. 
*   Use `surface-container-low` (#f6f3f2) to define secondary content zones against the main `background` (#fcf9f8).
*   Visual separation is achieved through white space (using the `spacing-16` or `spacing-20` tokens) rather than lines.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers. 
*   **The Base:** `surface` (#fcf9f8).
*   **The Inset:** Use `surface-container-highest` (#e5e2e1) for technical data blocks or mono-spaced accents to create a "recessed" look.
*   **The Float:** Use `surface-container-lowest` (#ffffff) for interactive cards to create a subtle "lift" against a `surface-container-low` background.

### The "Glass & Gradient" Rule
To capture the "interactive art experiment" vibe, use `primary-container` (#13a1d7) and `secondary-container` (#e81215) as soft, blurred radial gradients in the background of hero sections. Floating navigation elements should utilize a backdrop-blur (12px–20px) with `surface/80%` opacity to allow these gradients to bleed through, softening the technical precision with organic light.

---

## 3. Typography: Editorial Authority
Typography is the primary visual driver. We utilize high-contrast scaling to create a rhythmic hierarchy.

*   **Display (Google Sans):** Use `display-lg` (3.5rem) for hero statements. These should often be left-aligned with significant bottom margin (`spacing-12`) to allow the type to "own" the white space.
*   **Headlines (Google Sans):** `headline-lg` (2rem) is our workhorse for section titles. 
*   **Body (Google Sans Text):** Use `body-lg` (1rem) for long-form reading. The increased legibility of the "Text" variant ensures the creative flair doesn't compromise the fellowship's information density.
*   **Technical Accents (Google Sans Mono):** Use `label-md` (0.75rem) for meta-data, dates, and application IDs. This injects the "technical precision" into the layout, acting as a functional counter-balance to the large display type.

---

## 4. Elevation & Depth: Tonal Layering
We reject the heavy, muddy shadows of the early web. Depth in this system is ethereal and ambient.

*   **The Layering Principle:** Achieve hierarchy by stacking. A `surface-container-lowest` card sitting on a `surface-container-low` section creates a natural "paper on table" lift without a single drop shadow.
*   **Ambient Shadows:** For floating elements like the sticky bottom navigation, use a custom shadow: `0 20px 40px rgba(28, 27, 27, 0.06)`. It should feel like the component is hovering in a bright, evenly lit room.
*   **The "Ghost Border":** If a UI element (like an input field) requires a boundary for accessibility, use the `outline-variant` (#bdc8d0) at **15% opacity**. It should be felt, not seen.

---

## 5. Components

### Sticky Bottom Navigation
The "Anchor" of the experience. 
*   **Background:** `surface-container-lowest` with a 20px backdrop blur.
*   **Apply Button:** The signature `tertiary-container` (#ffb700). High-contrast black text (`on-tertiary-container`). Use `rounded-full` for this specific action to distinguish it from the architectural `rounded-sm` of other elements.
*   **Layout:** Use `spacing-4` padding. The button should feel like a physical "pill" floating within the nav bar.

### Buttons
*   **Primary:** `primary` (#00668a) with `rounded-sm` (0.125rem). The sharp corners reflect professional "studio" precision.
*   **Secondary/Tertiary:** No background. Use `primary` text with an underline that only appears on hover.

### Cards & Lists
*   **Constraint:** Zero dividers. 
*   **Implementation:** Group related items using a common `surface-container` background. Use `spacing-8` to separate distinct list items vertically.
*   **Interactive State:** On hover, a card should shift from `surface-container-low` to `surface-container-highest` with a `0.2s ease-out` transition.

### Input Fields
*   **Style:** Minimalist. No box. A single bottom stroke using `outline-variant` at 20% opacity. 
*   **Focus State:** The stroke transitions to `primary` (#00668a) and the label (Google Sans Mono) shifts upward using `label-sm`.

---

## 6. Do’s and Don’ts

### Do
*   **Do** embrace extreme asymmetry. Align a headline to the far left and a body paragraph to the mid-right.
*   **Do** use Google Sans Mono for all "meta" information (dates, tags, categories).
*   **Do** allow interactive elements to use the full Google brand palette as accent colors (e.g., a Green #00b213 "Success" chip).

### Don't
*   **Don’t** use 1px solid black borders. It breaks the "Gallery" feel and makes the UI look like a wireframe.
*   **Don’t** crowd the edges. If a component feels "snug," add another `spacing-4` of padding.
*   **Don’t** use standard "Material" shadows. If you can clearly see where the shadow ends, it's too dark.

---

## 7. Signature Interaction: The "Pulse"
Whenever a user interacts with a primary CTA or the sticky "Apply" button, use a subtle radial gradient expansion of the brand colors (`primary-container`) behind the element. This mimics the "interactive art experiment" vibe—where the UI reacts to the user's presence with light rather than just movement.```