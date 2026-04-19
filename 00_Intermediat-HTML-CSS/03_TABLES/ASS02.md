
### 1. Core Table Structure

| Element          | Purpose                                      | Placement & Notes |
|------------------|----------------------------------------------|-------------------|
| `<table>`        | Root container for tabular data              | Main wrapper; use only for real data, not layout |
| `<caption>`      | Visible title/description for the table      | First child of `<table>`; highly recommended for accessibility |
| `<thead>`        | Groups header rows                           | Can contain multiple rows; repeats on print |
| `<tbody>`        | Groups main data rows                        | Implicit if omitted; one or more allowed |
| `<tfoot>`        | Groups footer rows (e.g., totals)            | Can appear after `<tbody>` in HTML5 |
| `<tr>`           | Defines a table row                          | Must be inside `<thead>`, `<tbody>`, or `<tfoot>` |
| `<th>`           | Header cell (bold & centered by default)     | Use for column or row headers; can appear in `<tbody>` |
| `<td>`           | Data cell                                    | Regular content cells |

**Recommended Semantic Skeleton**:
```html
<table>
  <caption>Table description here</caption>
  <thead>...</thead>
  <tbody>...</tbody>
  <tfoot>...</tfoot>
</table>
```

### 2. Spanning & Cell Connection

| Attribute   | Description                              | Example |
|-------------|------------------------------------------|---------|
| `colspan`   | Cell spans multiple columns              | `<td colspan="3">Total</td>` |
| `rowspan`   | Cell spans multiple rows                 | `<td rowspan="2">Vertical span</td>` |
| `scope`     | Associates `<th>` with row/column/group  | `<th scope="col">` or `<th scope="row">` |
| `headers`   | Links `<td>` to specific `<th>` IDs      | `<td headers="id1 id2">` (for complex tables) |

**Tip**: Ensure the total "cell count" per row (accounting for spans) remains consistent for a rectangular layout.

### 3. Column Grouping

| Element     | Purpose                                      | Notes |
|-------------|----------------------------------------------|-------|
| `<colgroup>`| Groups columns for collective styling        | Place early in `<table>` (after `<caption>`) |
| `<col>`     | Styles one or more columns                   | Empty element; supports `span` attribute |

Example:
```html
<colgroup>
  <col span="2" class="main">
  <col class="total">
</colgroup>
```

### 4. Key CSS Properties for Tables

| Property                  | Description / Common Values                          | Example / Tip |
|---------------------------|------------------------------------------------------|---------------|
| `border-collapse`         | `collapse` (merges borders) or `separate`            | `collapse` is most common for clean grids |
| `border-spacing`          | Space between cells (only with `separate`)           | `border-spacing: 0.5rem;` |
| `padding`                 | Inner spacing of cells                               | `th, td { padding: 0.75rem 1rem; }` |
| `width`                   | Table or column width                                | `width: 100%;` for full container |
| `table-layout`            | `auto` (content-driven, default) or `fixed`          | `fixed` is faster and more predictable |
| `vertical-align`          | Aligns content inside cells                          | `middle`, `top`, `baseline` |
| `text-align`              | Horizontal text alignment                            | `left`, `center`, `right` |
| `white-space`             | Controls text wrapping                               | `nowrap` can force wider tables |

**Basic Styling Example**:
```css
table {
  border-collapse: collapse;
  width: 100%;
}
th, td {
  border: 1px solid #ccc;
  padding: 0.75rem;
  text-align: left;
}
```

### 5. Advanced Styling Techniques

| Technique               | CSS Selector / Rule                              | Purpose |
|-------------------------|--------------------------------------------------|---------|
| **Zebra Striping**      | `tbody tr:nth-child(odd) { background: #f9f9f9; }` | Alternating row colors for readability |
| **Row Hover**           | `tbody tr:hover { background: #f0f0f0; }`        | Highlight entire row on mouseover |
| **Cell Hover**          | `td:hover, th:hover { background: #ffffcc; }`    | Highlight individual cells |
| **Reset Defaults**      | `table { border-collapse: collapse; border-spacing: 0; }` | Removes browser spacing/padding |
| **Column Width Control**| Set widths on first row or use `<col>`           | Especially useful with `table-layout: fixed` |

### 6. Responsive Table Approaches (Pure CSS)

| Technique                  | Description                                                                 | When to Use |
|----------------------------|-----------------------------------------------------------------------------|-------------|
| **Stacking Rows**          | Change `display: block` on small screens; stack cells vertically            | Mobile-friendly data tables |
| **Hide Less Important Columns** | `@media (max-width: 600px) { .hide-mobile { display: none; } }`            | Prioritize key columns |
| **Allow Wrapping**         | Let text wrap naturally or use `white-space: normal`                        | Simple tables |
| **Fixed Header**           | `position: sticky; top: 0;` on `<th>` elements                              | Long scrolling tables |
| **De-table**               | Reset `display: block` / `inline` on table elements                         | Extreme mobile redesigns |

**Note**: Tables remain challenging on small screens. Prefer simpler data presentation when possible.

### 7. Accessibility & Best Practices

- Always include a `<caption>` for screen readers.
- Use `scope="col"` or `scope="row"` on `<th>` elements.
- Reserve tables for **tabular data** only (e.g., comparisons, schedules, financials).
- Avoid using tables for page layout (use CSS Grid or Flexbox instead).
- Test with screen readers and keyboard navigation.
- Deprecated attributes (e.g., `align`, `bgcolor`, `cellpadding`) → replace with CSS.

### 8. Quick Tips

- Browsers automatically imply `<tbody>` and close tags intelligently.
- Emmet shortcut example: `table>thead>tr>th*4^^tbody>tr*5>td*4` (quick skeleton).
- Column styling via `<col>` works for certain properties (background, width, etc.).
- For very wide tables: Wrap in `<div style="overflow-x: auto;">`.
- `table-layout: fixed` + widths on first row gives predictable column sizing.

