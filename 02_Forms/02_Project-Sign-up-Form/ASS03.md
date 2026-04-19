

### Project Implementation Guidelines

| # | Guideline | Details & How to Implement |
|---|---------|----------------------------|
| **1** | **Scaffolding Strategy** | Start by building the overall HTML structure first, then style section by section.<br>**Recommended order:**<br>1. Main container (flex layout)<br>2. Left sidebar (image + overlay)<br>3. Right side (form area)<br>4. Form fields & button |
| **2** | **Logo Background Overlay** | The area behind “ODIN” logo needs a **dark semi-transparent background**.<br>Use: `background-color: rgba(0, 0, 0, 0.5);` or `rgba(0, 0, 0, 0.6);`<br>Apply to a `<div>` that wraps the logo + text. |
| **3** | **Create Account Button Color** | Exact color given: **`#596D48`** (a muted green that matches the forest image).<br>Use this for the main submit button background. |
| **4** | **Password Input Validation** | Password fields should show a **red border** when invalid.<br>Use the **`:invalid`** pseudo-class.<br>Example:<br>`input[type="password"]:invalid { border-color: #e74c3c; }` |
| **5** | **Focused Input Style** | Selected/focused inputs should have a **blue border + subtle box-shadow**.<br>Use the **`:focus`** pseudo-class.<br>Example:<br>`input:focus { border-color: #4a90e2; box-shadow: 0 0 0 3px rgba(74, 144, 226, 0.2); }` |
| **6** | **Mobile Responsiveness** | **Do NOT** make it responsive yet.<br>Focus only on desktop layout (the design is desktop-first). Responsive design comes later in the curriculum. |
| **7** | **Password Matching** | Do **not** validate that both password fields match each other yet.<br>This requires JavaScript (covered in a future lesson).<br>For now, validate each password field individually using HTML5 constraints. |

### Recommended HTML Structure Outline

| Section | Suggested HTML Elements |
|---------|--------------------------|
| **Main Container** | `<div class="container">` with `display: flex;` |
| **Left Sidebar** | `<div class="sidebar">`<br>  `background-image`<br>  `div.overlay` (for dark background)<br>  `div.logo` (Odin logo + text) |
| **Right Side (Form)** | `<div class="form-side">`<br>  Header text<br>  `<form>`<br>  Fieldsets or divs for inputs<br>  Submit button |
| **Footer / Credit** | Small text at bottom with image credit |

### Key Colors to Use

| Element                    | Color Value     | Usage |
|----------------------------|-----------------|-------|
| Create Account Button      | `#596D48`       | Background color |
| Default Input Border       | `#E5E7EB`       | Light gray border |
| Invalid Password Border    | Red (`#e74c3c` or similar) | `:invalid` state |
| Focused Input Border       | Blue (`#4a90e2` or similar) | `:focus` state |

### Quick CSS Starter Snippets

```css
/* Sidebar Overlay */
.sidebar .overlay {
  background-color: rgba(0, 0, 0, 0.55);
}

/* Button */
button[type="submit"] {
  background-color: #596D48;
}

/* Default Input */
input {
  border: 1px solid #E5E7EB;
}

/* Focused Input */
input:focus {
  border-color: #4a90e2;
  box-shadow: 0 0 0 3px rgba(74, 144, 226, 0.2);
}

/* Invalid Password */
input[type="password"]:invalid {
  border-color: #e74c3c;
}
```

### Important Reminders

- Use semantic HTML (`<form>`, `<label>`, `<fieldset>` if it helps).
- Always associate labels properly with `for` attribute.
- Focus on desktop layout only for now.
- Password confirmation matching → leave for JavaScript lesson.

