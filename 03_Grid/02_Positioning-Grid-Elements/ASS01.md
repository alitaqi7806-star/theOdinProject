

### Line-based Placement in CSS Grid

| Concept                        | Description                                                                 | Syntax Example |
|--------------------------------|-----------------------------------------------------------------------------|----------------|
| **Grid Lines**                 | Numbered lines that define the grid structure (both horizontal and vertical) | Lines start at 1 from the start edge |
| **Explicit Lines**             | Lines created by `grid-template-columns` and `grid-template-rows`           | — |
| **Line-based Placement**       | Positioning grid items by referencing specific line numbers or names        | Most precise way to place items |
| **Two Ways to Place Items**    | 1. Using `grid-column` + `grid-row`<br>2. Using `grid-area` (shorthand)    | Both are commonly used |

### Core Properties for Line-based Placement

| Property                  | What It Controls                                      | Syntax Examples |
|---------------------------|-------------------------------------------------------|-----------------|
| `grid-column`             | Start and end column line numbers                     | `grid-column: 1 / 4;`<br>`grid-column: 2 / span 3;` |
| `grid-row`                | Start and end row line numbers                        | `grid-row: 1 / 3;`<br>`grid-row: 2 / span 2;` |
| `grid-area`               | Shorthand for `grid-row` + `grid-column`              | `grid-area: 1 / 2 / 3 / 5;` |
| `grid-column-start`       | Starting column line                                  | `grid-column-start: 2;` |
| `grid-column-end`         | Ending column line                                    | `grid-column-end: 5;` |
| `grid-row-start`          | Starting row line                                     | `grid-row-start: 1;` |
| `grid-row-end`            | Ending row line                                       | `grid-row-end: span 3;` |

### Span Keyword (Most Useful)

| Usage                         | Meaning                                              | Example |
|-------------------------------|------------------------------------------------------|---------|
| `span N`                      | Span across N tracks (most common)                   | `grid-column: span 3;` |
| `span` with line name         | Span until a named line                              | `grid-column: span main-content;` |
| Combining start + span        | Start at a line and span from there                  | `grid-column: 2 / span 4;` |

### Line Numbering Rules

| Rule                          | Details |
|-------------------------------|---------|
| Numbering starts at **1**     | First line is always line 1 |
| Negative numbering            | You can count backwards from the end (`-1` is the last line) |
| Example                       | `grid-column: 1 / -1;` → spans from first to last column |

### Named Lines (Advanced but Powerful)

| Feature                       | Syntax Example |
|-------------------------------|----------------|
| Define named lines            | `grid-template-columns: [main-start] 1fr [content-start] 2fr [content-end] 1fr [main-end];` |
| Reference named lines         | `grid-column: main-start / main-end;` |
| Multiple names on one line    | `[sidebar-start sidebar] 200px` |

### Shorthand: `grid-area`

| Syntax                              | Equivalent Long Form |
|-------------------------------------|----------------------|
| `grid-area: row-start / col-start / row-end / col-end;` | `grid-row: row-start / row-end;`<br>`grid-column: col-start / col-end;` |
| `grid-area: 1 / 2 / 4 / 5;`         | Spans from row 1 to 4, column 2 to 5 |

### Practical Examples

| Goal                                      | Best Property |
|-------------------------------------------|---------------|
| Place item in column 2, spanning 3 tracks | `grid-column: 2 / span 3;` |
| Place item from row 1 to row 3            | `grid-row: 1 / 3;` |
| Make item span entire grid width          | `grid-column: 1 / -1;` |
| Use named lines                           | `grid-column: header-start / header-end;` |

### Key Takeaways from MDN

- Line-based placement gives you **precise control** over where each item sits.
- `span` is the most commonly used keyword.
- You can mix line numbers and `span`.
- Named lines make code much more readable in complex grids.
- `grid-area` is the cleanest shorthand when placing items that span both rows and columns.
