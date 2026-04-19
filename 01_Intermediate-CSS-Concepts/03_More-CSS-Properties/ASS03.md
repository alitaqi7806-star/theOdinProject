
### Overview
The `border-radius` property rounds the corners of an element's outer border edge (and clips the background even if no border is visible). It supports circular or elliptical corners and is a shorthand for the four longhand properties.

### Shorthand Syntax
```css
border-radius: <length | percentage>{1,4} [ / <length | percentage>{1,4} ]?;
```

- Values before `/` = **horizontal** radius
- Values after `/` = **vertical** radius (for elliptical corners)
- All values must be non-negative

### How 1–4 Values Work (Horizontal Radii)

| Number of Values | Applies To                                      | Example                          |
|------------------|-------------------------------------------------|----------------------------------|
| **1 value**      | All four corners the same                       | `border-radius: 10px;`          |
| **2 values**     | Top-left & bottom-right<br>Top-right & bottom-left | `border-radius: 20px 5px;`      |
| **3 values**     | Top-left<br>Top-right & bottom-left<br>Bottom-right | `border-radius: 10px 20px 5px;` |
| **4 values**     | Top-left, top-right, bottom-right, bottom-left  | `border-radius: 10px 20px 30px 40px;` |

### Longhand Properties

| Property                    | Description                          |
|-----------------------------|--------------------------------------|
| `border-top-left-radius`    | Rounds the top-left corner           |
| `border-top-right-radius`   | Rounds the top-right corner          |
| `border-bottom-right-radius`| Rounds the bottom-right corner       |
| `border-bottom-left-radius` | Rounds the bottom-left corner        |

Each longhand can take 1 or 2 values (`horizontal / vertical`).

### Value Types

| Type         | Description                                                                 | Example          |
|--------------|-----------------------------------------------------------------------------|------------------|
| `<length>`   | Fixed size (`px`, `em`, `rem`, etc.)                                        | `15px`, `2em`    |
| `<percentage>` | Relative to element size<br>→ Horizontal % based on **width**<br>→ Vertical % based on **height** | `50%`, `20%`     |

### Elliptical Corners (Using `/`)

| Syntax Example                     | Result                                      |
|------------------------------------|---------------------------------------------|
| `border-radius: 20px / 10px;`      | All corners: horizontal 20px, vertical 10px |
| `border-radius: 50% / 20%;`        | Elliptical corners (oval shape)             |
| `border-radius: 10px 30px / 20px 40px;` | Different radii per corner (horizontal / vertical) |

### Common Patterns & Examples

| Goal                  | Code Example                                      | Notes |
|-----------------------|---------------------------------------------------|-------|
| **Uniform rounding**  | `border-radius: 12px;`                            | Most common for cards/buttons |
| **Fully rounded (circle)** | `border-radius: 50%;`                            | Element must be square (same width & height) |
| **Pill / capsule shape** | `border-radius: 9999px;` or `50%` (on tall element) | Creates rounded ends |
| **Different corners** | `border-radius: 20px 0 40px 10px;`                | Top-left 20px, top-right 0, etc. |
| **Elliptical**        | `border-radius: 80% 20% / 50% 30%;`               | Creates more organic/oval corners |
| **Reset**             | `border-radius: 0;`                               | Removes rounding |

### Important Notes & Gotchas

- **Background clipping** — The background is automatically clipped to the rounded shape (even without a visible border).
- **Tables** — `border-radius` is ignored on `<table>` elements when `border-collapse: collapse;`.
- **Negative values** — Not allowed.
- **Inheritance** — The shorthand does not support partial inheritance (use longhands if needed).
- **Animation** — Fully animatable (great for hover effects and transitions).
- **Browser Support** — Widely supported in all modern browsers since 2015.
- **Related properties** — `border`, `background-clip`, `corner-shape` (for advanced corner shapes like bevel/notch).

### Quick Tips
- Use `px` or `rem` for consistent rounding across the site.
- Use `%` for responsive/scalable rounding.
- Combine with `overflow: hidden;` on parent elements when needed.
- For modern designs, small values (8–16px) are very popular for cards and buttons.

**Example – Modern Card**
```css
.card {
  border-radius: 16px;
  overflow: hidden;           /* Ensures content respects rounding */
  background: white;
}
```

