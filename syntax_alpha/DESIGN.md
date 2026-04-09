# Design System Strategy: The Syntax Protocol

## 1. Overview & Creative North Star
**Creative North Star: "The Sovereign Terminal"**

This design system transcends the "hacker" cliché by treating the interface as a high-fidelity, sovereign financial instrument. It is not merely a "dark mode" skin; it is a curated editorial environment where data is the architecture. By leveraging intentional asymmetry, monospaced precision, and high-contrast tonal layering, we transform a trading journal into a digital cockpit. 

The system rejects the "web-template" look in favor of **Structural Brutalism**. We use the precision of code syntax—brackets, underscores, and comment tags—to organize information, creating a signature visual language that feels both authoritative and dangerously efficient.

---

## 2. Colors
Our palette is rooted in absolute depth, utilizing high-chroma neon accents to draw the eye to critical financial data.

*   **Primary Navigation & CTA:** `primary` (#d0ffa6) and `primary_container` (#88fe00). These are your "execution" colors. Use them for active trade buttons and profitable percentages.
*   **The Tonal Foundation:** The background starts at `surface` (#0e0e0e), but the logic of the UI is defined by its containers.

### The "No-Line" Rule
Standard 1px solid borders are strictly prohibited for sectioning. Structural boundaries must be defined through:
1.  **Background Shifts:** Place a `surface_container_lowest` (#000000) section inside a `surface` (#0e0e0e) background to create a "well" effect.
2.  **Tonal Transitions:** Use `surface_container_high` (#1f1f1f) to lift interactive panels without the need for an outline.

### Surface Hierarchy & Nesting
Treat the UI as a series of nested modules. 
*   **Level 0 (Base):** `surface` (#0e0e0e).
*   **Level 1 (Sections):** `surface_container_low` (#131313).
*   **Level 2 (Data Cards):** `surface_container_highest` (#262626).

### Signature Textures & Glass
To provide "visual soul," use a subtle linear gradient on primary action elements (from `primary` to `primary_dim`). For floating command palettes, implement **Glassmorphism**: use `surface_variant` at 60% opacity with a `40px` backdrop blur. This ensures the "terminal" feels deep and multi-layered, rather than a flat 2D screen.

---

## 3. Typography
The typography system utilizes `spaceGrotesk` to mimic the technical precision of monospaced fonts while maintaining the readability of a high-end editorial piece.

*   **Display (The PnL):** Use `display-lg` for total portfolio balance. Tracking should be set to `-0.02em` to feel tight and aggressive.
*   **Headlines (The Assets):** `headline-sm` is reserved for ticker symbols (e.g., $BTC, $ETH).
*   **Labels (The Metadata):** `label-sm` is used for "code-style" annotations. Prepend these with double slashes (e.g., `// TRADE_LOG_01`) to reinforce the terminal aesthetic.
*   **Hierarchy Note:** All data-heavy numbers must use `title-md` to ensure they stand out against descriptive body text.

---

## 4. Elevation & Depth
In this system, "Elevation" is synonymous with "Glow."

*   **Tonal Layering:** Avoid drop shadows for structural elements. Instead, use "stacking." A `surface_container_lowest` card placed on a `surface_container` background creates an "inset" feel, mimicking a terminal command line.
*   **The Glow (Ambient Shadows):** When an element must "float" (like a trade confirmation modal), use an ambient shadow tinted with `primary_container` (#88fe00) at 10% opacity, with a blur radius of at least `32px`. This simulates the neon glow of a CRT monitor.
*   **The "Ghost Border" Fallback:** If a container requires a border for accessibility, use the `outline_variant` (#484848) at **15% opacity**. This creates a "barely-there" structural guide that disappears into the background, maintaining the "No-Line" philosophy.

---

## 5. Components

### Buttons (The Commands)
*   **Primary:** `primary_container` background with `on_primary` text. No rounded corners (`0px`).
*   **Secondary:** `outline` ghost border (20% opacity) with `primary` text.
*   **Interaction:** On hover, the button should gain a `4px` outer glow of `primary_dim`.

### Input Fields (The Syntax)
*   Inputs should not look like boxes. They are underscores or bracketed areas. 
*   **Default:** A bottom-only border using `outline_variant`. 
*   **Active:** Prepend a green `>` character to the input text. Use `primary` for the cursor.

### Chips (The Tags)
*   Use `surface_container_highest` for the background. 
*   Format: `[ TAG_NAME ]`. The brackets are part of the component's visual DNA.

### Cards & Trading Lists
*   **Prohibition:** No divider lines between list items. 
*   **Solution:** Use alternating background tiers (`surface_container_low` vs `surface_container_lowest`) or intentional vertical white space (16px - 24px) to separate trades.

### The "Terminal Log" (Context Specific)
A dedicated component for trade history. Use `body-sm` with a lower opacity `on_surface_variant` (#ababab) for timestamps, making the actual trade data in `primary` pop as the "active" code.

---

## 6. Do's and Don'ts

### Do:
*   **Do** use monospaced alignment for all numerical data. Columns must line up perfectly.
*   **Do** use "code syntax" as ornamentation. Use `[]`, `{}`, `//`, and `>` as decorative elements to guide the eye.
*   **Do** embrace asymmetry. If a dashboard has a heavy data table on the left, balance it with a large-scale, low-opacity "comment" in the background on the right.

### Don't:
*   **Don't** use border-radius. Every corner in this system must be a sharp `0px`.
*   **Don't** use standard "Success Green" or "Alert Red" from a generic library. Use our `primary` (#d0ffa6) and `error` (#ff7351) tokens to maintain the high-end editorial tone.
*   **Don't** use 100% opaque lines. If a line is needed, it must be "Ghosted" (reduced opacity) or replaced by a tonal shift.