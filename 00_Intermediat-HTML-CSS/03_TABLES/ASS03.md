
### Assessment Overview

**Task**: Turn raw solar system planet data into a clean, accessible HTML table with proper grouping, spanning, and accessibility features.

**Caption**:  
“Data about the planets of our solar system (Planetary facts taken from NASA’s Planetary Fact Sheet - Metric).”

**Main Requirements**:
- Use `<table>`, `<caption>`, `<thead>`, `<tbody>`
- Add `<colgroup>` + `<col>` for special styling on the name column
- Use `<th>` for all headers (column and row)
- Proper `scope` attributes for accessibility
- Row/column spanning (`rowspan` / `colspan`) for planet group headings
- Planet names as row headers
- Notes column for extra text (some with links)

### Table Structure Cheat Sheet

| Section / Element       | Purpose & How to Use                                                                 | Key Attributes / Tips |
|-------------------------|--------------------------------------------------------------------------------------|-----------------------|
| `<table>`               | Main container                                                                       | Add `class` or inline styles if needed |
| `<caption>`             | Visible title for the table (first child)                                            | Must include the exact NASA text |
| `<colgroup>`            | Groups columns for styling                                                           | Place right after `<caption>` |
| `<col class="column-border">` | Applies special 2px black border to the **Name** column only                  | First `<col>` targets the name column |
| `<thead>`               | Column headers                                                                       | One `<tr>` with headers |
| First header cell       | Empty cell in top-left                                                               | `<th colspan="2"></th>` (spans Name + empty column) |
| Data column headers     | Mass, Diameter, Density, Gravity, etc.                                               | Use `<th scope="col">` |
| `<tbody>`               | All planet data + group headings                                                     | Contains group rows + planet rows |
| Group heading row       | "Terrestrial planets", "Jovian planets", etc.                                        | Use `<th rowspan="N" scope="rowgroup">` (N = number of planets in group) |
| Planet row              | One row per planet                                                                   | First cell: `<th scope="row">Planet Name</th>` |
| Data cells              | Mass, Diameter, etc.                                                                 | `<td>` elements |
| Notes column            | Extra information (some with links)                                                  | Last column |

### Column Headers (in order)

1. **Name** (special bordered column)
2. (Empty / spacer column)
3. **Mass (10²⁴kg)**
4. **Diameter (km)**
5. **Density (kg/m³)**
6. **Gravity (m/s²)**
7. **Length of day (hours)**
8. **Distance from Sun (10⁶ km)**
9. **Mean temperature (°C)**
10. **Number of moons**
11. **Notes**

### Planet Groups & Rowspans

| Group                  | Planets Included                  | Rowspan for Group Header |
|------------------------|-----------------------------------|--------------------------|
| Terrestrial planets    | Mercury, Venus, Earth, Mars       | 4 |
| Jovian planets         | Jupiter, Saturn                   | 2 (sometimes split further into Gas giants / Ice giants in some versions) |
| Ice giants             | Uranus, Neptune                   | 2 |
| Dwarf planets*         | Pluto                             | 1 |

**Note**: In the official example, "Jovian planets" is the main group, with "Ice giants" as a sub-group under it in some layouts. Use `rowspan` on the group name to cover all planets below it.

### Accessibility Best Practices (Must Include)

- Always add `<caption>`
- Use `scope="col"` on top column headers
- Use `scope="row"` on planet name cells
- Use `scope="rowgroup"` on group category headers (e.g., Terrestrial planets)
- Prefer simple `scope` over complex `id` + `headers` (as hinted in the assessment)
- Make sure screen readers can correctly associate headers with data

### Quick Emmet / Skeleton Tip

A fast way to start the skeleton:
```
table>caption+colgroup>col.column-border+col^^thead>tr>th[colspan=2]+th*9^^tbody
```

Then add group rows with `rowspan` and planet rows.

### Final Tips for Success

- The first column gets a thick black border via the `column-border` class on `<col>`.
- Group headings go in their own `<tr>` and use `rowspan` to stretch down over their planets.
- Planet names are row headers (`<th scope="row">`).
- 
