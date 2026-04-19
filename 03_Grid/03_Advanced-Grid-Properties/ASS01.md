

### 1. CSS Grid Properties

#### Grid Container Properties

| Property                        | Description                                                                 | Common Values / Examples |
|---------------------------------|-----------------------------------------------------------------------------|--------------------------|
| `display`                       | Establishes a new grid formatting context                                   | `grid` \| `inline-grid` |
| `grid-template-columns`         | Defines the columns of the grid (explicit tracks)                           | `100px 1fr 2fr`, `repeat(3, 1fr)`, `minmax(200px, 1fr)` |
| `grid-template-rows`            | Defines the rows of the grid (explicit tracks)                              | `auto 1fr auto`, `repeat(4, 150px)` |
| `grid-template-areas`           | Defines named grid areas for easier placement                               | `"header header" "sidebar main" "footer footer"` |
| `grid-template`                 | Shorthand for `grid-template-rows` + `grid-template-columns` + `grid-template-areas` | — |
| `gap` (or `grid-gap`)           | Sets spacing between rows **and** columns                                   | `20px`, `1rem 2rem` |
| `row-gap` / `column-gap`        | Sets spacing for rows or columns individually                               | `row-gap: 1rem;` |
| `justify-items`                 | Aligns grid items along the **inline** (horizontal) axis                   | `start` \| `end` \| `center` \| `stretch` (default) |
| `align-items`                   | Aligns grid items along the **block** (vertical) axis                      | `start` \| `end` \| `center` \| `stretch` |
| `place-items`                   | Shorthand for `align-items` + `justify-items`                               | `center stretch` |
| `justify-content`               | Aligns the entire grid along the **inline** axis when there's extra space  | `start` \| `end` \| `center` \| `space-between` \| `space-around` |
| `align-content`                 | Aligns the entire grid along the **block** axis when there's extra space   | Same as above |
| `place-content`                 | Shorthand for `align-content` + `justify-content`                           | — |
| `grid-auto-columns`             | Size of implicitly created columns                                          | `minmax(100px, auto)` |
| `grid-auto-rows`                | Size of implicitly created rows                                             | `minmax(150px, auto)` |
| `grid-auto-flow`                | Controls how auto-placed items are placed (row or column)                   | `row` (default) \| `column` \| `dense` |

#### Grid Item Properties

| Property                        | Description                                                                 | Common Values / Examples |
|---------------------------------|-----------------------------------------------------------------------------|--------------------------|
| `grid-column`                   | Shorthand for placing item by column line numbers                           | `2 / 5`, `span 3`, `1 / -1` |
| `grid-row`                      | Shorthand for placing item by row line numbers                              | `1 / 3`, `span 2` |
| `grid-area`                     | Shorthand for `grid-row-start` / `grid-column-start` / `grid-row-end` / `grid-column-end` | `2 / 3 / 4 / 6` |
| `justify-self`                  | Aligns a single item along the inline axis                                  | `start` \| `center` \| `end` |
| `align-self`                    | Aligns a single item along the block axis                                   | `start` \| `center` \| `end` |
| `place-self`                    | Shorthand for `align-self` + `justify-self`                                 | — |

### 2. Special Units, Values, & Functions

| Unit / Function                 | Description                                                                 | Example |
|---------------------------------|-----------------------------------------------------------------------------|---------|
| **`fr`** (fraction)             | Fractional unit — distributes remaining space proportionally                | `grid-template-columns: 1fr 2fr 1fr;` |
| **`minmax(min, max)`**          | Sets a track size with a minimum and maximum value                          | `minmax(200px, 1fr)` |
| **`auto`**                      | Fits content size (similar to `min-content` in many cases)                  | `grid-auto-rows: auto;` |
| **`repeat()`**                  | Repeats a pattern of tracks                                                 | `repeat(3, 1fr)`, `repeat(auto-fit, minmax(200px, 1fr))` |
| **`auto-fit`**                  | Creates as many tracks as possible, collapsing empty ones                   | `repeat(auto-fit, minmax(250px, 1fr))` |
| **`auto-fill`**                 | Creates as many tracks as possible, keeping empty ones                      | `repeat(auto-fill, minmax(200px, 1fr))` |
| **`fit-content()`**             | Sizes track based on content but respects max size                          | `fit-content(300px)` |

### 3. Subgrid

| Concept                         | Description                                                                 | Example |
|---------------------------------|-----------------------------------------------------------------------------|---------|
| **What is Subgrid?**            | Allows a nested grid to inherit track sizes and line names from its parent grid | Enables perfect alignment across nested elements |
| `grid-template-columns: subgrid` | Child grid inherits the **columns** from the parent                         | `grid-template-columns: subgrid;` |
| `grid-template-rows: subgrid`   | Child grid inherits the **rows** from the parent                            | `grid-template-rows: subgrid;` |
| **How to Use**                  | 1. Parent defines explicit tracks<br>2. Child spans area + sets `subgrid`   | Child can then place its own items using parent's lines |
| **Benefit**                     | Solves alignment problems in nested card layouts, lists, etc.               | No more manual syncing of track sizes |
| **Note**                        | `display: contents;` is **not** subgrid — it's a different tool            | Subgrid is specifically for inheriting grid tracks |

### Quick Summary Takeaways

- **Grid Container** properties define the overall structure (`grid-template-*`, `gap`, alignment).
- **Grid Item** properties control individual placement (`grid-column`, `grid-row`, `grid-area`).
- **`fr`** unit + `minmax()` + `repeat()` are the most powerful tools for flexible grids.
- **`subgrid`** is excellent for complex nested layouts where alignment across levels matters.

