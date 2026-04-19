

### CSS `position` Property Cheat Sheet

| Position Value     | Default / Behavior in Document Flow                          | Offset Properties (top, right, bottom, left) | Reference Point (Containing Block)                  | Removes from Normal Flow? | Common Use Cases                              | Key Notes / Gotchas |
|--------------------|-------------------------------------------------------------|----------------------------------------------|-----------------------------------------------------|---------------------------|-----------------------------------------------|---------------------|
| **`static`**       | Normal document flow (default value)                        | Ignored                                      | Normal flow                                         | No                        | Default layout, everything unless changed     | Most elements start here. Offsets do nothing. |
| **`relative`**     | Behaves like `static` but can be shifted                    | Works (moves relative to its normal position) | Itself (original position in flow)                  | No (space is reserved)    | Slight adjustments, creating positioning context for children | Element still occupies its original space. Good parent for absolute children. |
| **`absolute`**     | Completely removed from flow                                | Works                                        | Nearest **positioned** ancestor (not `static`) or initial containing block (viewport) | **Yes**                   | Tooltips, modals inside containers, overlays, icons inside cards | If no positioned ancestor exists, it uses the viewport. |
| **`fixed`**        | Removed from flow                                           | Works                                        | **Viewport** (browser window)                       | **Yes**                   | Sticky navbars, floating action buttons, chat widgets | Stays in the same screen position even when scrolling. |
| **`sticky`**       | Hybrid: starts like `relative`, then behaves like `fixed`   | Works (threshold)                            | Nearest scrolling ancestor (usually viewport)       | No (until threshold)      | Sticky headers, table headers, side navigation | Switches to fixed-like behavior when it hits the offset (e.g. `top: 0`). |

### How Offsets Work (`top`, `right`, `bottom`, `left`)

- Positive `top` → moves the element **down**.
- Positive `left` → moves the element **right**.
- You can use any combination (e.g. `top: 20px; left: 50px;`).
- For `absolute` and `fixed`, offsets are measured from the edges of the containing block.
- For `relative`, offsets are measured from the element’s original position.

### Quick Comparison Table

| Feature                        | `static` | `relative` | `absolute` | `fixed` | `sticky` |
|--------------------------------|----------|------------|------------|---------|----------|
| Follows normal document flow   | Yes      | Yes        | No         | No      | Yes (until threshold) |
| Can use top/right/bottom/left  | No       | Yes        | Yes        | Yes     | Yes      |
| Creates new stacking context   | No       | Sometimes  | Yes        | Yes     | Yes      |
| Scrolls with page content      | Yes      | Yes        | Yes (with parent) | No   | Yes → No (when stuck) |
| Best for overlays / popups     | —        | —          | Excellent  | Good    | —        |
| Best for persistent UI         | —        | —          | —          | Excellent | Excellent (headers) |

### Important Concepts Explained in the Video

1. **Containing Block / Positioning Context**  
   - `absolute` looks for the closest ancestor with `position` other than `static` (usually `relative`).  
   - If none found → uses the initial containing block (viewport).

2. **Z-Index**  
   - Only works on positioned elements (`relative`, `absolute`, `fixed`, `sticky`).  
   - Higher value = appears on top.

3. **Common Patterns**
   - Parent with `position: relative` + Child with `position: absolute` → Perfect for positioning inside a container.
   - `position: fixed` for elements that must stay on screen while scrolling.
   - `position: sticky` for headers that scroll normally then stick at the top.

4. **Best Practices**
   - Prefer `relative` + `absolute` combinations over deep nesting.
   - Use `fixed` sparingly (it can hurt mobile performance if overused).
   - Test sticky positioning carefully — it depends on the scrolling container.
   - Always consider accessibility (e.g., fixed elements shouldn't hide important content).

### One-Line Summary for Each

- **Static** — Normal flow. Do nothing special.
- **Relative** — Normal flow + slight nudge.
- **Absolute** — Pull it out and place it exactly where I want inside a container.
- **Fixed** — Glue it to the screen, ignore scrolling.
- **Sticky** — Scroll normally, then glue when it reaches the edge.

This cheat sheet captures the fast-paced visual explanations from the video, including how each position interacts with document flow and other elements.

**Video Link**: https://www.youtube.com/watch?v=jx5jmI0UlXU  
**Companion Article**: https://blog.webdevsimplified.com/2022-01/css-position/

