

### Discovering & Toggling Grids

| Feature                  | How to Use                                                                 | What It Shows |
|--------------------------|----------------------------------------------------------------------------|---------------|
| **Grid Badge**           | In **Elements** panel, look for the `grid` badge next to any element with `display: grid` or `display: inline-grid` | Click to toggle the grid overlay on/off |
| **Grid Overlay**         | Click the grid badge or use controls in the Layout pane                    | Visual overlay showing grid lines, tracks, and items on the page |

### Main Inspection Area: Layout Pane

When you select a grid container in the **Elements** panel, the **Layout** pane (usually on the right) shows a dedicated **Grid** section with powerful controls.

| Section / Option                  | Description                                                                 | How to Use |
|-----------------------------------|-----------------------------------------------------------------------------|------------|
| **Overlay Display Settings**      | Controls how the grid overlay looks                                         | Dropdowns and checkboxes in the Grid section |
| **Line Labels**                   | Choose what appears on grid lines                                           | Options: Show line numbers (default), Hide line labels, Show line names |
| **Show Track Sizes**              | Displays authored size vs computed (actual rendered) size for each track    | Checkbox – very useful for debugging `fr`, `auto`, `minmax()` etc. |
| **Show Area Names**               | Shows named grid areas defined with `grid-template-areas`                   | Checkbox |
| **Extend Grid Lines**             | Extends grid lines all the way to the viewport edges                        | Checkbox – helps see alignment across the page |
| **Grid Overlays List**            | Lists all grids currently on the page                                       | Toggle visibility, change overlay color per grid, highlight/scroll to element |

### Grid Editor (Quick Alignment Tool)

| Feature                       | What It Allows You to Do                                      | How to Access |
|-------------------------------|---------------------------------------------------------------|---------------|
| **Grid Editor**               | Visually set alignment properties without writing CSS         | In **Styles** pane, click the grid icon next to `display: grid` |
| **Supported Properties**      | `align-items`, `justify-items`, `align-content`, `justify-content` | Click buttons in the editor UI – changes apply live |

### Useful Visualization & Debugging Features

| Feature                        | Benefit                                                                 | Tip |
|--------------------------------|-------------------------------------------------------------------------|-----|
| **Track Sizes Display**        | Shows both the size you wrote in CSS and the actual rendered size       | Especially helpful with `fr` units and flexible tracks |
| **Multiple Grid Overlays**     | View several grids at once with different colors                        | Great for nested grids or complex layouts |
| **Color Picker per Grid**      | Customize overlay color for each grid                                   | Makes it easier to distinguish overlapping grids |
| **Highlight Icon**             | Scroll to the element and select it in the DOM tree                     | Quick navigation |

### Quick Workflow Summary

1. Open **DevTools** → **Elements** panel.
2. Find an element with `display: grid` → click the **grid** badge to enable overlay.
3. Go to the **Layout** pane → use the **Grid** section for detailed controls.
4. Use **Show track sizes** and **Show area names** for deep inspection.
5. Click the **Grid Editor** icon in the Styles pane for quick alignment experiments.

### Pro Tips

- The **grid badge** is the fastest way to toggle the overlay.
- Always enable **Show track sizes** when debugging flexible grids (`fr`, `auto`, `minmax()`).
- Use different colors when inspecting multiple or nested grids.
- The Grid Editor is excellent for experimenting with alignment properties visually.

