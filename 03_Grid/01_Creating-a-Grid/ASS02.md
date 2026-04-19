

### Implicit vs Explicit Tracks in CSS Grid

| Aspect                      | **Explicit Tracks**                                      | **Implicit Tracks**                                      |
|-----------------------------|----------------------------------------------------------|----------------------------------------------------------|
| **Definition**              | Tracks you **manually define** in your CSS               | Tracks that are **automatically created** by the browser |
| **How to Create**           | Using `grid-template-columns` and `grid-template-rows`   | Created when grid items need more space than explicitly defined |
| **Control**                 | You have full control over size and number               | Browser automatically adds rows or columns as needed |
| **Main Properties**         | `grid-template-columns`<br>`grid-template-rows`          | `grid-auto-rows`<br>`grid-auto-columns`                  |
| **Default Behavior**        | Only the tracks you specify exist                        | Implicit tracks are created in the direction of `grid-auto-flow` (default = `row`) |
| **Common Use Case**         | Defining the main grid structure (e.g. 3 columns)        | Handling extra items that don’t fit in your defined grid |
| **Size Control**            | You set exact sizes (`200px`, `1fr`, `repeat()`, etc.)  | Controlled by `grid-auto-rows` / `grid-auto-columns` |

### Visual Comparison

| Scenario                                 | Explicit Tracks                          | Implicit Tracks Created |
|------------------------------------------|------------------------------------------|--------------------------|
| You define `grid-template-columns: 1fr 1fr 1fr;` | 3 columns                                | None initially |
| You place 5 items in the grid            | First 3 items fill the explicit columns  | Browser creates 2 more rows automatically |
| You define only 2 rows                   | 2 explicit rows                          | Extra rows created implicitly |

### Key Properties for Implicit Tracks

| Property                    | What It Controls                              | Common Values / Example |
|-----------------------------|-----------------------------------------------|-------------------------|
| `grid-auto-rows`            | Height of automatically created **rows**      | `grid-auto-rows: 150px;`<br>`grid-auto-rows: minmax(100px, auto);` |
| `grid-auto-columns`         | Width of automatically created **columns**    | `grid-auto-columns: 200px;` |
| `grid-auto-flow`            | Direction in which implicit tracks are created | `row` (default), `column`, `dense` |

### Important Behaviors Explained

| Behavior                                 | Explanation |
|------------------------------------------|-----------|
| **Default Direction**                    | Implicit tracks are created in the **row** direction by default (`grid-auto-flow: row;`) |
| **Dense Packing**                        | `grid-auto-flow: dense;` fills gaps by placing later items into earlier holes |
| **Minmax is Your Friend**                | Best practice: `grid-auto-rows: minmax(100px, auto);` so implicit rows grow with content |
| **Explicit vs Implicit**                 | Explicit = You define it.<br>Implicit = Browser adds it when content overflows |
| **Mixing Both**                          | Most real-world grids combine explicit structure with implicit fallback |

### Quick Code Examples

```css
/* Explicit Tracks */
.grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);     /* 3 explicit columns */
  grid-template-rows: 200px 200px;           /* 2 explicit rows */
  gap: 20px;
}

/* Implicit Tracks */
.grid {
  grid-auto-rows: minmax(150px, auto);       /* All extra rows will be at least 150px */
  grid-auto-columns: 250px;                  /* Extra columns (if needed) */
  grid-auto-flow: row;                       /* Default: fill row by row */
}
```

### Wes Bos Key Takeaways

- Understand the difference early — it prevents many frustrating layout bugs.
- Always set `grid-auto-rows` (and sometimes `grid-auto-columns`) for better control over implicit tracks.
- Use `minmax()` with implicit tracks to allow content to breathe.
- `grid-auto-flow: dense` can dramatically improve layout when you have irregularly sized items.

This cheat sheet captures the core concepts taught in the short Wes Bos video on **Implicit vs Explicit Tracks**.

