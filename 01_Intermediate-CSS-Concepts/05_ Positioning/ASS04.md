

### Fixed vs Sticky: Core Comparison

| Aspect                        | `position: fixed`                                      | `position: sticky`                                              |
|-------------------------------|--------------------------------------------------------|-----------------------------------------------------------------|
| **Initial Behavior**          | Removed from normal document flow immediately          | Behaves like `relative` / normal flow until threshold          |
| **When Scrolling**            | Stays fixed to the **viewport** at all times           | Scrolls normally with content until it reaches the offset, then **sticks** |
| **Reference Point**           | Viewport (browser window)                              | Its own position in flow, then sticks relative to viewport      |
| **Containing Block**          | Viewport (with rare edge cases)                        | Its **parent / containing block**                               |
| **Out of Flow?**              | Yes — completely removed                               | No — stays in flow until it sticks                              |
| **Space Reserved**            | No                                                     | Yes (until it sticks)                                           |
| **What Happens When Parent Scrolls Off Screen** | Stays visible on screen                                | Scrolls away with its parent/container                          |
| **Required Offset**           | `top`, `right`, `bottom`, `left` (or `inset`)          | At least one offset on the sticking axis (usually `top: 0`)     |

### Key Differences Highlighted by Kevin Powell

| Feature / Behavior                  | `position: fixed`                                      | `position: sticky`                                              | Winner / Recommendation |
|-------------------------------------|--------------------------------------------------------|-----------------------------------------------------------------|-------------------------|
| **Stays on screen forever**         | Yes                                                    | No — only sticks while its parent is visible                    | Fixed                   |
| **Respects parent container**       | No (ignores parent boundaries)                         | Yes — cannot escape its containing block                        | Sticky                  |
| **Good for full-page persistent UI**| Excellent (navbars, floating buttons)                  | Not ideal                                                       | Fixed                   |
| **Good for section-specific headers**| Can work but may overlap content awkwardly             | Excellent (table headers, article sub-headers)                  | Sticky                  |
| **Layout impact**                   | Breaks normal flow — you often need to add margin/padding to compensate | Preserves flow better                                           | Sticky                  |
| **Browser support & performance**   | Excellent                                              | Excellent (modern browsers)                                     | Tie                     |

### Common Use Cases

| Use Case                              | Recommended Position | Why |
|---------------------------------------|----------------------|-----|
| Main navigation / header that stays at top of screen | `fixed`             | Should remain visible even when scrolling long content |
| Sticky section header inside a long article or card | `sticky`            | Sticks only while that section is in view |
| Table header that sticks while scrolling table content | `sticky`            | Behaves well inside its container |
| Floating action button (FAB)          | `fixed`             | Must stay in corner regardless of scroll |
| Sidebar that sticks during scrolling a page | `sticky` (preferred) or `fixed` | Sticky respects page layout better |
| Modal or tooltip                      | Usually `fixed` or `absolute` | Not typically sticky |

### Quick Code Examples

**Fixed (always on screen):**
```css
.navbar {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
}
```

**Sticky (sticks only within its parent):**
```css
.section-header {
  position: sticky;
  top: 0;           /* required threshold */
  background: white;
  z-index: 10;
}
```

### Important Gotchas from the Article

- **Sticky needs a threshold** — without `top`/`bottom`/etc., it behaves like `relative`.
- **Sticky is constrained by its parent** — once the parent scrolls off screen, the sticky element goes with it.
- **Fixed can have rare edge cases** where it’s not fixed to the viewport (e.g., when an ancestor has certain transforms).
- Sticky is often the better choice for headers inside scrollable content because it respects the document flow and doesn’t require extra spacing adjustments.

### One-Line Summary (Kevin Powell Style)

- **`fixed`** = “Glue this to the screen forever, no matter what.”
- **`sticky`** = “Scroll normally with everything else, but when you reach this point, act like `fixed` — but only while your parent is still visible.”

This cheat sheet captures the practical differences, real-world use cases, and insights from Kevin Powell’s article.

**Original Article**: https://www.kevinpowell.co/article/positition-fixed-vs-sticky/
