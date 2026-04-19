

### 1. Core Table Elements

| Element          | Description                                      | Placement / Notes |
|------------------|--------------------------------------------------|-------------------|
| `<table>`        | Root container for tabular data                  | Main wrapper |
| `<tr>`           | Table row                                        | Groups cells horizontally |
| `<td>`           | Table data cell (regular content)                | Must be inside `<tr>` |
| `<th>`           | Table header cell (bold & centered by default)   | Use for column/row headers |
| `<caption>`      | Visible table title/description                  | First child of `<table>` (highly recommended for accessibility) |

### 2. Table Structure (Recommended Full Skeleton)

```html
<table>
  <caption>Table description</caption>
  <colgroup>…</colgroup>          <!-- optional -->
  <thead>…</thead>
  <tbody>…</tbody>
  <tfoot>…</tfoot>
</table>
```

### 3. Spanning Attributes

| Attribute   | Description                        | Example |
|-------------|------------------------------------|---------|
| `colspan`   | Cell spans multiple **columns**    | `<td colspan="3">Total</td>` |
| `rowspan`   | Cell spans multiple **rows**       | `<td rowspan="2">Horse</td>` |

**Tip**: Always calculate spans carefully — missing cells will break the table layout.

### 4. Grouping Elements

| Element     | Purpose                                      | Notes |
|-------------|----------------------------------------------|-------|
| `<thead>`   | Header section (column headings)             | Can repeat on print |
| `<tbody>`   | Main data body                               | Implicit if omitted, but add explicitly |
| `<tfoot>`   | Footer section (e.g., totals, summaries)     | Place before `<tbody>` in code for rendering order |
| `<colgroup>`| Groups one or more columns for styling       | Immediately after `<table>` or `<caption>` |
| `<col>`     | Defines a single column or group of columns  | Child of `<colgroup>`, supports `span` attribute |

### 5. Accessibility Attributes

| Attribute / Feature | Value / Usage                          | Purpose |
|---------------------|----------------------------------------|---------|
| `scope`             | `col`, `row`, `colgroup`, `rowgroup`   | Associates header with column, row, or group (screen readers) |
| `<caption>`         | Text description                       | Visible title read first by assistive tech |
| `id` + `headers`    | On `<td>`: `headers="id1 id2"`         | Manual linking for very complex tables |
| ARIA roles          | `role="table"`, `role="columnheader"`, etc. | Usually not needed if native semantics are correct |

**Best Practice**: Always use `<th>` with proper `scope` instead of plain `<td>` for headers.

### 6. Column Grouping Example

```html
<table>
  <caption>Monthly Expenses</caption>
  <colgroup>
    <col span="2" class="category">
    <col class="amount">
  </colgroup>
  <thead>
    <tr>
      <th scope="col">Item</th>
      <th scope="col">Description</th>
      <th scope="col">Cost</th>
    </tr>
  </thead>
  <tbody>
    …
  </tbody>
</table>
```

### 7. Common CSS Styling for Tables

| Goal                    | CSS Example |
|-------------------------|-------------|
| Clean borders           | `table { border-collapse: collapse; }`<br>`td, th { border: 1px solid #ccc; padding: 8px 12px; }` |
| Zebra striping          | `tr:nth-child(even) { background: #f9f9f9; }` |
| Header styling          | `th { background: #eee; text-align: left; }` |
| Section-specific        | `thead th { font-weight: bold; }`<br>`tfoot td { font-weight: bold; }` |
| Responsive (scrollable) | Wrap table: `<div style="overflow-x: auto;"> <table>...</table> </div>` |

### 8. Quick Tips & Best Practices

- **Tables are for tabular data only** — never use them for page layout (use CSS Grid/Flexbox instead).
- Place `<caption>` right after `<table>` opening tag.
- Use `<thead>`, `<tbody>`, and `<tfoot>` for better semantics, printing, and styling.
- Prefer `scope` attribute for simple-to-medium complexity tables.
- Test with screen readers and keyboard navigation.
- Default browser table styling is ugly — always add CSS for readability.
- For very complex tables, combine `colspan`/`rowspan` with `scope="colgroup"` or `scope="rowgroup"`.

### 9. Minimal Complete Example

```html
<table>
  <caption>Student Grades</caption>
  <thead>
    <tr>
      <th scope="col">Name</th>
      <th scope="col">Math</th>
      <th scope="col">Science</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">Ali</th>
      <td>92</td>
      <td>88</td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <td colspan="2">Average</td>
      <td>90</td>
    </tr>
  </tfoot>
</table>
```

