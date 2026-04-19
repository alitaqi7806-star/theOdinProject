
### What is the Holy Grail Layout?

| Section          | Position                  | Typical Content                  | Behavior |
|------------------|---------------------------|----------------------------------|----------|
| **Header**       | Top, full width           | Logo + Navigation                | Spans all columns |
| **Left Sidebar** | Left column               | Navigation / Widgets             | Fixed width |
| **Main Content** | Center column             | Primary article / content        | Flexible (takes remaining space) |
| **Right Sidebar**| Right column              | Ads / Secondary widgets          | Fixed width |
| **Footer**       | Bottom, full width        | Copyright / Links                | Spans all columns |

### Recommended HTML Structure

```html
<body>
  <div class="holy-grail">
    <header>Header</header>
    
    <div class="sidebar-left">Left Sidebar</div>
    <main>Main Content Area</main>
    <div class="sidebar-right">Right Sidebar</div>
    
    <footer>Footer</footer>
  </div>
</body>
```

### CSS Grid Solution (Core Properties)

| Property                        | Recommended Value                                      | Purpose |
|---------------------------------|--------------------------------------------------------|---------|
| `display`                       | `grid`                                                 | Turns the container into a grid |
| `grid-template-columns`         | `200px 1fr 200px` (or `minmax(200px, 250px) 1fr minmax(200px, 250px)`) | Left sidebar – flexible center – right sidebar |
| `grid-template-rows`            | `auto 1fr auto`                                        | Header – growing main area – footer |
| `gap`                           | `1rem` or `20px`                                       | Spacing between all tracks |
| `min-height`                    | `100vh` (on the grid container)                        | Makes the layout fill the viewport height |

### Line-based Placement for Each Section

| Section            | Property Used                     | Value Example                          | Explanation |
|--------------------|-----------------------------------|----------------------------------------|-------------|
| **Header**         | `grid-column`                     | `1 / -1`                               | Spans from first to last column |
| **Left Sidebar**   | `grid-column`                     | `1` or `1 / 2`                         | Occupies first column |
| **Main Content**   | `grid-column`                     | `2` or `2 / 3`                         | Occupies middle column |
| **Right Sidebar**  | `grid-column`                     | `3` or `3 / 4`                         | Occupies third column |
| **Footer**         | `grid-column`                     | `1 / -1`                               | Spans full width |

### Alternative: Using `grid-template-areas` (Clean & Readable)

```css
.holy-grail {
  display: grid;
  grid-template-columns: 200px 1fr 200px;
  grid-template-rows: auto 1fr auto;
  grid-template-areas:
    "header header header"
    "left   main   right"
    "footer footer footer";
  gap: 20px;
  min-height: 100vh;
}

header   { grid-area: header; }
.left    { grid-area: left; }
main     { grid-area: main; }
.right   { grid-area: right; }
footer   { grid-area: footer; }
```

### Quick Tips for This Exercise

- Use **Flexbox** on the header and footer internally if you need horizontal navigation.
- Make the center column grow with `1fr`.
- Set a reasonable fixed width for both sidebars (200px–250px is common).
- Add some background colors and padding to clearly see each section.
- Don’t worry about responsiveness (this exercise is desktop-only).

### Common Mistakes to Avoid

- Forgetting `grid-column: 1 / -1;` on header and footer.
- Not setting `min-height: 100vh` on the grid container.
- Using wrong line numbers (remember they start at 1).
- Not making the main content area flexible (`1fr`).
