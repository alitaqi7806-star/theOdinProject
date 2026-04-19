
### CSS Grid Garden – Levels 18 to 28 Cheat Sheet

| Level | Goal / What You Need to Do                              | Correct Property & Value                                      | Key Concept Taught |
|-------|---------------------------------------------------------|---------------------------------------------------------------|--------------------|
| 18    | Water the plants using `grid-template-areas`           | `grid-template-areas: "a a a" "b c d" "e e e";`              | Defining named areas with `grid-template-areas` |
| 19    | Place items using named areas                           | `grid-area: b;` (or `c`, `d`, etc.)                           | Using `grid-area` with named areas |
| 20    | Create a more complex area layout                       | `grid-template-areas: "header header" "sidebar main" "footer footer";` | Real-world area naming pattern |
| 21    | Water the plants by assigning areas                     | Assign each plant its correct `grid-area`                     | Mapping items to named areas |
| 22    | Use both line numbers and named areas                   | Mix `grid-column`, `grid-row`, and `grid-area`                | Combining different placement methods |
| 23    | Water the plants using named lines                      | Define named lines in `grid-template-columns` / `rows`        | Named grid lines |
| 24    | Place items using named lines                           | `grid-column: left / right;` or `grid-row: top / bottom;`     | Referencing named lines |
| 25    | Create a layout with both named areas and named lines   | Combine `grid-template-areas` with named lines                | Advanced hybrid approach |
| 26    | Water the plants with a complex named layout            | Carefully define and assign multiple named areas              | Complex area-based layouts |
| 27    | Use `grid-template-areas` with repeating patterns       | Use `repeat()` inside `grid-template-areas` (if needed)       | Scaling area layouts |
| 28    | Final challenge – combine everything                    | Mix `grid-template-areas`, named lines, `span`, and `grid-area` | Comprehensive review of all placement techniques |

### Most Important Techniques Covered (Levels 18–28)

| Technique                        | Syntax Example                                               | When to Use |
|----------------------------------|--------------------------------------------------------------|-------------|
| **`grid-template-areas`**        | `grid-template-areas: "header header" "sidebar main";`       | When you want readable, semantic layout definitions |
| **`grid-area`**                  | `.plant { grid-area: main; }`                                | Assigning an item to a named area |
| **Named Lines**                  | `grid-template-columns: [left] 200px [main-start] 1fr [main-end] 200px [right];` | When you need precise control with meaningful names |
| **Combining Methods**            | Use `grid-area` for some items and `grid-column` / `grid-row` for others | Complex or irregular layouts |
| **Line Names in Areas**          | Define line names and then reference them in placement       | Large-scale or component-based grids |

### Quick Reference Summary

| Concept                     | Best Property / Approach                     |
|-----------------------------|----------------------------------------------|
| Simple rectangular areas    | `grid-template-areas` + `grid-area`          |
| Complex or overlapping      | Named lines + `grid-column` / `grid-row`     |
| Readability & maintenance   | Prefer `grid-template-areas`                 |
| Precision                   | Line numbers or named lines                  |
| Mixed layouts               | Combine `grid-area` with `grid-column`/`grid-row` |

### Pro Tips from Levels 18–28

- `grid-template-areas` makes your code much more readable — think of it like drawing the layout with words.
- Named lines are powerful when you have many items that need to align to the same vertical or horizontal positions.
- You can mix and match: some items placed with `grid-area`, others with line numbers.
- Always check the hint on the right — it often tells you whether to use areas or line-based placement.

**Play the game here**: https://cssgridgarden.com/
