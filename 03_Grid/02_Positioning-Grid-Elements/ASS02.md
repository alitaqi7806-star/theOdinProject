

### CSS Grid Garden – Levels 1 to 17 Cheat Sheet

| Level | Goal / What You Need to Do                          | Correct Property & Value                          | Key Concept Learned |
|-------|-----------------------------------------------------|---------------------------------------------------|---------------------|
| 1     | Water the carrot (place one item)                   | `grid-column: 3;`                                 | Basic column placement |
| 2     | Water the carrot                                    | `grid-column: 5;`                                 | Using higher column numbers |
| 3     | Water all carrots in one row                        | `grid-column: 1 / -1;` or `grid-column: span 5;` | Spanning all columns |
| 4     | Water the carrots in column 3                       | `grid-column: 3;`                                 | Targeting specific column |
| 5     | Water the carrots using row placement               | `grid-row: 3;`                                    | Basic row placement |
| 6     | Water multiple carrots using rows                   | `grid-row: 2 / 4;`                                | Spanning multiple rows |
| 7     | Water the carrots using both row and column         | `grid-column: 2 / 4;`<br>`grid-row: 2 / 4;`       | Combining row + column |
| 8     | Water the carrots using `span`                      | `grid-column: span 3;`                            | Using `span` keyword |
| 9     | Water the carrots with negative line numbers        | `grid-column: 2 / -1;`                            | Negative line numbering |
| 10    | Water the carrots using named lines                 | `grid-column: carrot-start / carrot-end;`         | Named grid lines |
| 11    | Water only the middle carrots                       | `grid-column: 2 / 5;`                             | Precise column range |
| 12    | Water the carrots using `grid-area` shorthand       | `grid-area: 2 / 2 / 4 / 5;`                       | `grid-area` shorthand |
| 13    | Water the carrots by spanning from a starting line  | `grid-column: 3 / span 3;`                        | Start line + `span` |
| 14    | Water the carrots in a specific area                | `grid-area: 2 / 3 / 5 / 6;`                       | Defining a rectangular area |
| 15    | Water the carrots using negative span               | `grid-column: 1 / span -2;`                       | Negative span (less common) |
| 16    | Water all the carrots except the first two          | `grid-column: 3 / -1;`                            | From line 3 to the end |
| 17    | Water the carrots using a combination of techniques | Mix of `grid-column`, `grid-row`, and `span`      | Review & combining concepts |

### Quick Reference: Most Important Properties (Levels 1–17)

| Property            | Common Usage Examples                          | Meaning |
|---------------------|------------------------------------------------|---------|
| `grid-column`       | `2`, `1 / 4`, `span 3`, `2 / span 3`, `1 / -1` | Controls horizontal placement |
| `grid-row`          | `3`, `2 / 5`, `span 2`                         | Controls vertical placement |
| `grid-area`         | `2 / 3 / 5 / 6`                                | Shorthand for row + column |
| `span` keyword      | `span 3`, `3 / span 4`                         | Span across multiple tracks |

### Key Concepts Covered in Levels 1–17

- Placing items using column and row line numbers
- Using the `span` keyword (very important)
- Combining `grid-column` and `grid-row`
- Using `grid-area` shorthand
- Negative line numbers (`-1` = last line)
- Starting at a specific line and spanning from there
- Understanding that line numbers start at **1**

### Pro Tips from Playing the Game

- Line numbers start at **1** from the left/top edge.
- `grid-column: 1 / -1;` = spans the entire width.
- `span` is usually the cleanest way to make items larger.
- `grid-area` is great when an item spans both rows and columns.
- Always check the hint on the right — it tells you exactly which property to use.

**Game Link**: https://cssgridgarden.com/

