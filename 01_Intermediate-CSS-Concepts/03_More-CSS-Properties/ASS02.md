

### 1. Border Shorthand

The `border` property is a **shorthand** that sets `border-width`, `border-style`, and `border-color` in one declaration.

**Syntax**:
```css
border: <line-width> <line-style> <color>;
```
- The order of values **does not matter**.
- You can provide **1, 2, or 3 values**.
- If any value is omitted, it falls back to the default.

**Examples**:
- `border: 2px solid red;`          (width + style + color)
- `border: 1px dashed;`             (width + style)
- `border: solid blue;`             (style + color)
- `border: 3px;`                    (width only)

**Important Note**: The border will be **invisible** if `border-style` is `none` (default) or `hidden`.

### 2. Individual Longhand Properties

| Property              | Values                                                                 | Default Value     | Description |
|-----------------------|------------------------------------------------------------------------|-------------------|-------------|
| `border-width`        | `thin` \| `medium` \| `thick` \| `<length>` (e.g., `2px`, `0.5em`)    | `medium`          | Sets the thickness of the border |
| `border-style`        | `none` \| `hidden` \| `dotted` \| `dashed` \| `solid` \| `double` \| `groove` \| `ridge` \| `inset` \| `outset` | `none`            | Defines the style (appearance) of the border |
| `border-color`        | Any valid color (`red`, `#ff0000`, `rgb(255 0 0)`, `currentColor`, etc.) | `currentColor`    | Sets the color of the border |

### 3. Side-Specific Shorthands

These allow you to set different borders on each side:

| Shorthand Property     | Description                                      | Example |
|------------------------|--------------------------------------------------|---------|
| `border-top`           | Top border only                                  | `border-top: 2px solid black;` |
| `border-right`         | Right border only                                | `border-right: 1px dashed gray;` |
| `border-bottom`        | Bottom border only                               | `border-bottom: 3px double blue;` |
| `border-left`          | Left border only                                 | `border-left: 4px outset red;` |

You can also use more granular properties:
- `border-top-width`, `border-top-style`, `border-top-color`
- `border-right-width`, etc.
- `border-bottom-width`, etc.
- `border-left-width`, etc.

### 4. Border Style Values

| Style Value   | Visual Appearance                  | Common Use |
|---------------|------------------------------------|------------|
| `none`        | No border (invisible)              | Default |
| `hidden`      | No border (same as none in most cases) | Tables |
| `solid`       | Straight solid line                | Most common |
| `dashed`      | Dashed line                        | Decorative |
| `dotted`      | Dotted line                        | Subtle borders |
| `double`      | Two parallel solid lines           | Emphasis |
| `groove`      | 3D grooved (carved) effect         | 3D look |
| `ridge`       | 3D ridged (raised) effect          | 3D look |
| `inset`       | 3D inset (sunken) effect           | 3D look |
| `outset`      | 3D outset (raised) effect          | 3D look |

### 5. Related Properties

| Property           | Purpose                                              | Notes |
|--------------------|------------------------------------------------------|-------|
| `border-radius`    | Rounds the corners of the border                     | Accepts 1–4 values (e.g., `8px`, `50%`) |
| `border-image`     | Uses an image as the border                          | Not affected by the `border` shorthand |
| `outline`          | Similar to border but does **not** take up space     | Often used for focus states |

### 6. Quick Tips & Best Practices

- Use the `border` shorthand when all four sides are the same.
- Use side-specific properties (`border-top`, etc.) when sides differ.
- Always set `border-style` — otherwise the border remains invisible.
- `border-color` defaults to `currentColor` (inherits the element’s text color).
- Borders take up space in the **box model** (unlike `outline`).
- For rounded borders: `border-radius: 8px;` or `border-radius: 50%;` (for circles).
- Modern approach: Combine with `border` + `border-radius` for clean cards and buttons.

**Common Example** (a typical card border):
```css
.card {
  border: 1px solid #ddd;        /* shorthand */
  border-radius: 12px;
  padding: 1rem;
}
```

