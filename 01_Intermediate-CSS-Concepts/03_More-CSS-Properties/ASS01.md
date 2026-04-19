
### 1. Background Shorthand Property

The `background` property is a **shorthand** that sets multiple background styles in one declaration.

**Syntax** (one or more layers, comma-separated):
```css
background: <bg-image> <bg-position> / <bg-size> <bg-repeat> <bg-attachment> <bg-clip> <bg-origin> <bg-color>;
```

**Recommended value order** (for readability):
`background-image` → `background-position` → `/` `background-size` → `background-repeat` → `background-attachment` → `background-clip` → `background-origin` → `background-color`

**Key Rules**:
- Multiple backgrounds are separated by commas (first layer is topmost).
- `background-color` can **only** appear in the **last** layer.
- Missing values fall back to their defaults.

**Example** (multiple layers):
```css
background: 
  center / contain no-repeat url("logo.svg"),
  #f0f0f0 50% url("pattern.png");
```

### 2. Individual Background Properties

| Property                  | Syntax / Values                                                                 | Default Value      | Description |
|---------------------------|---------------------------------------------------------------------------------|--------------------|-------------|
| `background-color`        | `<color>` (e.g., `#fff`, `rgb(255 0 0)`, `transparent`)                        | `transparent`      | Sets the background color. Only allowed in the final layer of the shorthand. |
| `background-image`        | `none` \| `<image>` (url(), gradient, image-set(), etc.)                       | `none`             | Specifies one or more background images. Layers are painted from top to bottom. |
| `background-position`     | `<position>` (keywords: `center`, `top`, `left`, etc. + lengths/percentages)   | `0% 0%`            | Sets the starting position of the background image(s). First value = horizontal, second = vertical. |
| `background-size`         | `auto` \| `cover` \| `contain` \| `<length-percentage>` (1 or 2 values)        | `auto`             | Controls the size of the background image. Use `/` after position in shorthand. `cover` fills the area (may crop); `contain` fits entirely (may leave gaps). |
| `background-repeat`       | `repeat` \| `repeat-x` \| `repeat-y` \| `no-repeat` \| `space` \| `round`      | `repeat`           | Defines how the background image is repeated (tiled) horizontally and vertically. |
| `background-attachment`   | `scroll` \| `fixed` \| `local`                                                  | `scroll`           | Determines whether the background scrolls with the content (`scroll`), stays fixed (`fixed`), or scrolls with the element's content (`local`). |
| `background-origin`       | `border-box` \| `padding-box` \| `content-box`                                  | `padding-box`      | Sets the reference point (origin) for `background-position`. |
| `background-clip`         | `border-box` \| `padding-box` \| `content-box` \| `text`                        | `border-box`       | Defines the painting area (where the background is actually drawn/clipped). `text` clips to the text shape. |

### 3. Default Values Summary

| Property                  | Default          |
|---------------------------|------------------|
| `background-image`        | `none`           |
| `background-position`     | `0% 0%`          |
| `background-size`         | `auto`           |
| `background-repeat`       | `repeat`         |
| `background-attachment`   | `scroll`         |
| `background-origin`       | `padding-box`    |
| `background-clip`         | `border-box`     |
| `background-color`        | `transparent`    |

### 4. Common Patterns & Examples

| Goal                              | Code Example |
|-----------------------------------|--------------|
| **Solid color**                   | `background: #3498db;` |
| **Image with no repeat**          | `background: url("image.jpg") no-repeat center;` |
| **Image with size & position**    | `background: url("hero.jpg") center / cover no-repeat;` |
| **Gradient background**           | `background: linear-gradient(to right, #f00, #00f);` |
| **Multiple backgrounds**          | `background: url("top.png") top left no-repeat, url("bottom.png") bottom right no-repeat;` |
| **Fixed background (parallax effect)** | `background: url("bg.jpg") center / cover fixed;` |

### 5. Important Notes & Gotchas

- **Layer Order** — First listed layer appears on top; last layer is at the bottom.
- **Position + Size** — In shorthand, separate them with `/` (e.g., `center / 80%`).
- **Visual Box** — `background-origin` sets the positioning reference; `background-clip` sets the painting area.
- **Body / html Behavior** — Background styles on `<body>` can propagate to `<html>` under certain conditions (mainly when `<html>` has no background).
- **Accessibility** — Background images are not read by screen readers. Provide text alternatives if the image conveys important information.
- **Performance** — Large background images can slow down pages. Use `background-size: cover` carefully and optimize images.
- **Modern Tip** — Combine with `background-blend-mode` or `background-attachment: local` for advanced effects.

### Quick Tips
- Always include a fallback `background-color` for images.
- Use `background: none;` to reset backgrounds.
- Test `cover` and `contain` on different screen sizes.
- For complex designs, prefer the shorthand for brevity, but use longhand properties when you need precise control.

