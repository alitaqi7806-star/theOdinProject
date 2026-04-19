

### CSS Grid Layout – Introduction & Key Terms

| Section              | Key Concept                          | Definition / Explanation |
|----------------------|--------------------------------------|--------------------------|
| **What is CSS Grid?** | Two-dimensional layout system        | CSS Grid is a powerful layout method designed for creating complex two-dimensional layouts (rows **and** columns) on a webpage. |
| **Core Purpose**     | Layout in rows + columns             | Unlike Flexbox (one-dimensional), Grid excels at controlling both axes simultaneously. |
| **When to Use Grid** | Complex layouts                      | Best for overall page structure, galleries, card layouts, dashboards, and any design that needs precise row and column control. |
| **Browser Support**  | Excellent (modern browsers)          | Supported in all modern browsers since 2017. |

### Key Grid Terminology (Most Important Concepts)

| Term                     | Definition | Visual Explanation |
|--------------------------|----------|--------------------|
| **Grid Container**       | The parent element that has `display: grid;` applied | This element becomes the grid and holds all grid items |
| **Grid Item**            | Any direct child of the grid container | These are the elements placed inside the grid |
| **Grid Line**            | The dividing lines that form the grid structure (horizontal and vertical) | Lines numbered starting from 1 |
| **Grid Track**           | The space between two grid lines (a row or a column) | Rows are horizontal tracks, columns are vertical tracks |
| **Grid Cell**            | A single unit of the grid (intersection of one row and one column) | The smallest unit in the grid |
| **Grid Area**            | Any rectangular area made up of one or more grid cells | Can span multiple rows and columns |
| **Gap (Gutters)**        | Space between grid tracks (rows and columns) | Controlled with `gap`, `row-gap`, and `column-gap` |
| **Explicit Grid**        | Grid defined by `grid-template-rows` and `grid-template-columns` | You manually define the structure |
| **Implicit Grid**        | Automatically created rows/columns when content needs more space | Created when items exceed the explicit grid |

### Grid Properties Overview (Key Terms)

| Property Type               | Properties | Purpose |
|-----------------------------|----------|---------|
| **Container Properties**    | `display: grid;`<br>`grid-template-columns`<br>`grid-template-rows`<br>`grid-template-areas` | Define the overall grid structure |
| **Gap Properties**          | `gap`<br>`row-gap`<br>`column-gap` | Add space between tracks |
| **Item Placement**          | `grid-column`<br>`grid-row`<br>`grid-area` | Control where items sit in the grid |
| **Alignment**               | `justify-items`<br>`align-items`<br>`place-items`<br>`justify-content`<br>`align-content`<br>`place-content` | Align items and content inside the grid |

### Quick Summary Table (Must-Know Terms)

| Term                  | What It Controls                  | Analogy |
|-----------------------|-----------------------------------|--------|
| Grid Container        | The whole grid                    | The table |
| Grid Item             | Individual boxes inside grid      | Cells inside the table |
| Grid Line             | Lines that divide the grid        | Lines on ruled paper |
| Grid Track            | A row or a column                 | Row or column of the table |
| Grid Area             | Rectangle made of multiple cells  | A merged group of cells |
| Gap                   | Space between rows & columns      | Spacing between cells |

### Important Takeaways from the Introduction

- CSS Grid is **two-dimensional** — you can control rows **and** columns at the same time.
- It works alongside Flexbox — use Grid for page layout and Flexbox for component alignment.
- Grid is extremely powerful for complex, responsive layouts.
- Understanding the **terminology** (especially Grid Lines, Tracks, and Areas) is crucial before diving into actual properties.
