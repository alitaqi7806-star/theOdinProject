

### CSS `position` Property Overview

| Aspect                  | Details                                                                 |
|-------------------------|-------------------------------------------------------------------------|
| **Syntax**              | `position: static \| relative \| absolute \| fixed \| sticky;`        |
| **Initial Value**       | `static`                                                                |
| **Applies to**          | All elements                                                            |
| **Inherited**           | No                                                                      |
| **Computed Value**      | As specified                                                            |
| **Animation Type**      | Discrete (jumps between values)                                         |
| **Formal Syntax**       | `static \| relative \| absolute \| sticky \| fixed`                     |

### Positioning Values Comparison

| Value       | Document Flow Impact                          | Space Reserved? | Offset Properties (`top/right/bottom/left`) | Containing Block / Reference Point                          | Stacking Context Created? | Common Use Cases                              |
|-------------|-----------------------------------------------|-----------------|---------------------------------------------|-------------------------------------------------------------|---------------------------|-----------------------------------------------|
| **`static`** (default) | Normal flow                                   | Yes             | Ignored                                     | Normal flow position                                        | No                        | Default layout — use when no special positioning needed |
| **`relative`**     | Normal flow + offset from original position   | Yes             | Relative to its normal position             | Itself (original spot in flow)                              | If `z-index` ≠ `auto`     | Small nudges, positioning context for absolute children |
| **`absolute`**     | Removed from flow                             | No              | From edges of containing block              | Nearest **positioned** ancestor (not `static`) or initial containing block | If `z-index` ≠ `auto`     | Overlays, tooltips, popups, icons inside containers |
| **`fixed`**        | Removed from flow                             | No              | From viewport edges                         | Viewport (or transformed ancestor)                          | Always                    | Fixed navbars, floating buttons, chat widgets |
| **`sticky`**       | Normal flow until threshold, then sticks      | Yes (until stuck) | Threshold for sticking                      | Nearest scrolling ancestor                                  | Always                    | Sticky headers, table headers, sidebars       |

### Offset Properties (`top`, `right`, `bottom`, `left`)

- Work with **`relative`**, **`absolute`**, **`fixed`**, and **`sticky`**.
- **For `relative`**: Offset measured from the element’s **original position** in the flow.
- **For `absolute` / `fixed`**: Offset measured from the **edges** of the containing block.
- **For `sticky`**: Defines the **threshold** where the element starts sticking (e.g., `top: 0`).
- Logical properties (`inset-*`) are also available for modern layouts.

### Containing Block Rules

- **Absolute** elements look for the **closest ancestor** with `position` set to anything **except `static`**.
- If none found → uses the **initial containing block** (usually the viewport).
- **Fixed** is almost always relative to the **viewport**, unless an ancestor has `transform`, `perspective`, or `filter` (not `none`).
- **Sticky** uses the **nearest scrolling ancestor** (with `overflow` not `visible`).

### Stacking Context & `z-index`

- Positioned elements (`relative`, `absolute`, `fixed`, `sticky`) can create a new stacking context when `z-index` is not `auto`.
- `fixed` and `sticky` **always** create a stacking context.
- Higher `z-index` values appear on top within the same stacking context.

### Global Values

| Value      | Description                                      |
|------------|--------------------------------------------------|
| `inherit`  | Takes the computed value from the parent         |
| `initial`  | Sets to default (`static`)                       |
| `revert`   | Resets to user-agent or inherited value          |
| `unset`    | Acts as `inherit` or `initial` depending on inheritance |

### Key Notes & Behaviors

| Topic                        | Details |
|------------------------------|--------|
| **Margins**                  | Do **not** collapse on absolutely positioned elements |
| **Table elements**           | `relative` behavior can be undefined on table parts |
| **Sticky requirements**      | Needs at least one non-`auto` inset property (e.g., `top: 10px`) on the relevant axis |
| **Performance**              | `fixed` and `sticky` can cause repaint/jank during scroll — consider `will-change: transform` for heavy use |
| **Accessibility**            | Avoid `fixed`/`absolute` elements that hide content on zoom; ensure keyboard focus order remains logical |
| **Printing**                 | `fixed` elements appear in the same position on every printed page |

### Quick One-Line Summary

- **`static`** — Normal document flow (do nothing).
- **`relative`** — Normal flow + nudge (great parent for absolute children).
- **`absolute`** — Pull out of flow and position inside nearest positioned container.
- **`fixed`** — Glue to the viewport (stays while scrolling).
- **`sticky`** — Scroll normally, then stick at a threshold.

This cheat sheet covers the core conceptual details, formal definition, values, and behaviors from the MDN page on the `position` property.

**Official MDN Link**: https://developer.mozilla.org/en-US/docs/Web/CSS/position

