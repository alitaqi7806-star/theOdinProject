

### 1. Basic Native Form Controls (Original `<input>` Types)

| Control Type              | HTML Code Example                                      | Purpose / Behavior | Key Attributes | Notes |
|---------------------------|--------------------------------------------------------|--------------------|----------------|-------|
| **Text**                  | `<input type="text">`                                  | Single-line plain text | `name`, `value`, `placeholder`, `maxlength` | Default input type |
| **Password**              | `<input type="password">`                              | Masked password field | `name`, `value` | Hides characters |
| **Checkbox**              | `<input type="checkbox">`                              | Multiple selection (on/off) | `name`, `value`, `checked` | Can have same `name` for groups |
| **Radio**                 | `<input type="radio">`                                 | Single selection from a group | `name` (must be same for group), `value`, `checked` | All radios in a group share one `name` |
| **File**                  | `<input type="file">`                                  | File upload | `name`, `multiple`, `accept` | Use with `enctype="multipart/form-data"` |
| **Hidden**                | `<input type="hidden">`                                | Not visible to user | `name`, `value` | Used for passing data (e.g., tokens) |
| **Submit**                | `<input type="submit">`                                | Submits the form | `value` | Older way; prefer `<button type="submit">` |
| **Image**                 | `<input type="image">`                                 | Image as submit button | `src`, `alt` | Submits coordinates (x,y) |

### 2. HTML5 Input Types (Specialized Controls)

| Input Type                  | HTML Example                                      | Purpose / UI Widget | Key Attributes / Features | Browser Support Notes |
|-----------------------------|---------------------------------------------------|---------------------|---------------------------|-----------------------|
| **Email**                   | `<input type="email">`                            | Email address | `multiple` | Built-in validation |
| **URL**                     | `<input type="url">`                              | Web address | — | Built-in validation |
| **Tel**                     | `<input type="tel">`                              | Telephone number | `pattern` | No strict validation |
| **Number**                  | `<input type="number">`                           | Numeric value with spinner | `min`, `max`, `step` | Spinner UI |
| **Range**                   | `<input type="range">`                            | Slider | `min`, `max`, `step`, `value` | Slider control |
| **Color**                   | `<input type="color">`                            | Color picker | `value` (#hex) | Color wheel/palette |
| **Date**                    | `<input type="date">`                             | Date picker | `min`, `max` | Calendar widget |
| **Time**                    | `<input type="time">`                             | Time picker | `min`, `max`, `step` | Time selector |
| **Datetime-local**          | `<input type="datetime-local">`                   | Date + time | `min`, `max` | Combined picker |
| **Month** / **Week**        | `<input type="month">` / `<input type="week">`    | Month or week selection | `min`, `max` | Calendar-based |

### 3. Other Form Controls (Non-`<input>` Elements)

| Element                     | HTML Example                                                                 | Purpose | Key Attributes | Notes |
|-----------------------------|------------------------------------------------------------------------------|---------|----------------|-------|
| **Textarea**                | `<textarea rows="5" cols="30"></textarea>`                                   | Multi-line text input | `rows`, `cols`, `maxlength`, `placeholder` | Resizable by default |
| **Select** (Dropdown)       | `<select><option value="1">Option 1</option></select>`                       | Single selection dropdown | `name`, `multiple`, `size` | Use `<optgroup>` for grouping |
| **Button**                  | `<button type="submit">Submit</button>`                                      | Clickable button | `type` (`submit`, `reset`, `button`) | Preferred over `<input type="submit">` |
| **Datalist** + **Option**   | `<input list="list-id">`<br>`<datalist id="list-id">`<br>`<option value="...">` | Autocomplete suggestions | — | Works with text inputs |
| **Output**                  | `<output name="result"></output>`                                            | Displays calculation result | `for`, `name` | Often updated via JavaScript |
| **Progress**                | `<progress value="70" max="100"></progress>`                                 | Progress bar | `value`, `max` | Visual progress indicator |
| **Meter**                   | `<meter value="70" min="0" max="100" low="40" high="90"></meter>`           | Gauge / measurement | `value`, `min`, `max`, `low`, `high`, `optimum` | Semantic gauge |

### Quick Best Practices from MDN Guides

- Always pair controls with `<label>` using the `for` attribute.
- Use the same `name` for radio buttons in a group and for checkboxes that belong together.
- Prefer `<button type="submit">` over `<input type="submit">` for better styling and semantics.
- For file uploads, set `enctype="multipart/form-data"` on the `<form>`.
- Test keyboard navigation and screen reader support on all controls.

