

### 1. Syntax Overview

**Shorthand**:
```css
box-shadow: <offset-x> <offset-y> <blur-radius> <spread-radius> <color>? inset?;
```

- Multiple shadows are separated by commas (first listed = topmost layer).
- Minimum: 2 values (`offset-x` and `offset-y`).
- You can use 2, 3, 4, or 5 values per shadow.

**Default / Initial value**: `none`

### 2. Value Breakdown

| Value            | Description                                                                 | Default | Notes |
|------------------|-----------------------------------------------------------------------------|---------|-------|
| **offset-x**     | Horizontal offset of the shadow (positive = right, negative = left)        | 0       | Required |
| **offset-y**     | Vertical offset of the shadow (positive = down, negative = up)             | 0       | Required |
| **blur-radius**  | Amount of blur (larger = softer shadow). Must be ≥ 0.                      | 0       | Sharp edges when 0 |
| **spread-radius**| Expands (+) or contracts (-) the shadow size                               | 0       | Optional |
| **color**        | Color of the shadow (any valid CSS color)                                   | `currentColor` (inherits from element's `color`) | Optional |
| **inset**        | Keyword that creates an **inner** shadow (pressed-in effect)               | —       | Optional; placed at the end |

### 3. How Many Values You Provide

| Number of Values | Meaning                                                                 | Example |
|------------------|-------------------------------------------------------------------------|---------|
| 2                | `offset-x` `offset-y`                                                   | `5px 10px` |
| 3                | `offset-x` `offset-y` `blur-radius`                                     | `5px 10px 15px` |
| 4                | `offset-x` `offset-y` `blur-radius` `spread-radius`                     | `5px 10px 15px 3px` |
| 5                | `offset-x` `offset-y` `blur-radius` `spread-radius` `color`             | `5px 10px 15px 3px #000` |

### 4. Common Patterns & Examples

| Goal                          | Code Example                                                                 | Effect |
|-------------------------------|------------------------------------------------------------------------------|--------|
| **Basic drop shadow**         | `box-shadow: 4px 4px 8px rgba(0, 0, 0, 0.2);`                               | Soft outer shadow |
| **Soft elevated card**        | `box-shadow: 0 10px 20px rgba(0, 0, 0, 0.15);`                              | Modern floating card |
| **Inset (pressed) shadow**    | `box-shadow: inset 0 2px 4px rgba(0, 0, 0, 0.3);`                           | Inner / sunken effect |
| **Outline / glow effect**     | `box-shadow: 0 0 0 3px #3498db;`                                             | Solid colored outline |
| **Multiple shadows**          | `box-shadow: 0 4px 6px -1px rgb(0 0 0 / 0.1), 0 2px 4px -2px rgb(0 0 0 / 0.1);` | Layered realistic shadow |
| **Neumorphism**               | `box-shadow: 8px 8px 16px #d1d1d1, -8px -8px 16px #ffffff;`                 | Soft 3D pressed look |
| **Hover lift effect**         | `transition: box-shadow 0.3s;`<br>`:hover { box-shadow: 0 20px 25px -5px rgb(0 0 0 / 0.1); }` | Interactive depth |

### 5. Key Notes & Gotchas

- Shadows **do not** affect layout or box model dimensions (they can overflow).
- `inset` shadows are drawn **inside** the border, above the background, and below the content.
- Negative `blur-radius` is **not allowed**.
- When `border-radius` is present, the shadow automatically follows the rounded corners.
- Use `rgba()` or `rgb()` with alpha for natural blending and softer shadows.
- First shadow in the list is rendered on top (back-to-front order).
- For performance, avoid animating very complex or many shadows.

### 6. Related Properties & Tips

| Property / Technique       | Relation to box-shadow                                      |
|----------------------------|-------------------------------------------------------------|
| `border-radius`            | Shadow automatically rounds to match the element’s corners  |
| `filter: drop-shadow()`    | Alternative shadow (affects the element’s shape/alpha)      |
| `text-shadow`              | Similar syntax for text shadows                             |
| `outline`                  | Can mimic a simple outline but has no blur or spread        |

**Best Practices**:
- Prefer `rgba()` / `rgb()` with transparency for modern soft shadows.
- Combine with `transition` for smooth hover effects.
- Use small `spread-radius` (often negative) to make shadows tighter.
- Test on different backgrounds — shadows look different on light vs dark themes.
- For accessibility, ensure shadows provide enough contrast/depth without causing visual strain.

**Reset**:
```css
box-shadow: none;
```

