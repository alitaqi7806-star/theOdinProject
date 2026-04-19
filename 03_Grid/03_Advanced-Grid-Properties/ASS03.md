

- **01-responsive-holy-grail**
- **02-holy-grail-mockup**

### 1. 01-responsive-holy-grail

**Goal**: Turn the classic Holy Grail layout into a **responsive** version using CSS Grid.

| Aspect                        | Desktop (Large screens)                     | Tablet / Mobile (smaller screens)                  | Key Technique |
|-------------------------------|---------------------------------------------|----------------------------------------------------|---------------|
| **Main Layout**               | 3-column: sidebar – main – sidebar          | Single column (stacked)                            | Media Queries + Grid |
| `grid-template-columns`       | `200px 1fr 200px`                           | `1fr`                                              | Change column definition |
| `grid-template-rows`          | `auto 1fr auto`                             | `auto auto 1fr auto auto`                          | Add more rows for stacking |
| `grid-template-areas` (Recommended) | `"header header header"<br>"left main right"<br>"footer footer footer"` | `"header"<br>"left"<br>"main"<br>"right"<br>"footer"` | Best for responsiveness |
| **Sidebars**                  | Fixed width (200–250px)                     | Full width (stack below/above main)                | Re-order with `grid-template-areas` |
| **Main Content**              | Takes remaining space (`1fr`)               | Full width                                         | — |
| **Header & Footer**           | Full width (`1 / -1`)                       | Full width                                         | — |

#### Recommended Responsive Strategy

```css
.holy-grail {
  display: grid;
  grid-template-areas:
    "header"
    "left"
    "main"
    "right"
    "footer";
  gap: 1rem;
  min-height: 100vh;
}

/* Desktop / Large screens */
@media (min-width: 900px) {
  .holy-grail {
    grid-template-columns: 220px 1fr 220px;
    grid-template-areas:
      "header header header"
      "left   main   right"
      "footer footer footer";
  }
}
```

### 2. 02-holy-grail-mockup

**Goal**: Build a **pixel-perfect** or very close mockup of a realistic Holy Grail layout with proper content, colors, and details.

| Section              | Key Implementation Tips |
|----------------------|-------------------------|
| **Header**           | Use Flexbox inside for logo + navigation<br>Fixed or sticky height |
| **Left Sidebar**     | Navigation menu with links<br>Fixed or min-width |
| **Main Content**     | Article with heading, paragraphs, images<br>Use `1fr` to grow |
| **Right Sidebar**    | Widgets, ads, or secondary navigation<br>Fixed width |
| **Footer**           | Centered or distributed links + copyright |
| **Overall Container**| `min-height: 100vh`, `display: grid` |
| **Colors & Spacing** | Use consistent padding, gap, and background colors |

#### Best Practices for This Exercise

| Area                    | Recommendation |
|-------------------------|----------------|
| **Layout Method**       | Use `grid-template-areas` — it's the cleanest for this layout |
| **Responsiveness**      | Add at least one breakpoint (usually around 900px–1024px) |
| **Typography**          | Good contrast, readable font sizes, proper line-height |
| **Realism**             | Add realistic dummy content (headings, paragraphs, fake images) |
| **Accessibility**       | Proper heading hierarchy, semantic HTML, good contrast |
| **Naming**              | Use clear class names: `.header`, `.sidebar-left`, `.main-content`, etc. |

### Combined Quick Reference Table

| Exercise                    | Main Technique                  | Grid Properties to Focus On                     | Responsiveness Required? |
|-----------------------------|---------------------------------|-------------------------------------------------|--------------------------|
| **01-responsive-holy-grail**| Responsive Holy Grail           | `grid-template-areas`, media queries, `1fr`    | Yes                      |
| **02-holy-grail-mockup**    | Realistic Holy Grail Mockup     | `grid-template-areas`, `grid-template-columns`, alignment, content styling | Yes (recommended) |

### Pro Tips for Both Exercises

- Prefer `grid-template-areas` over line-based placement for readability.
- Use `minmax(200px, 250px)` for sidebars if you want them to have a reasonable minimum width.
- Always set `min-height: 100vh` on the grid container.
- For the mockup, spend time making the content look believable (not just colored boxes).
- Test your responsive version by resizing the browser window.
