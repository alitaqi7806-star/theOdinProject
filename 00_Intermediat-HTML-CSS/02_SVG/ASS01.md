

### SVG Fundamentals

| Concept                  | Description                                                                 | Key Takeaway / Tip |
|--------------------------|-----------------------------------------------------------------------------|--------------------|
| **What is SVG?**        | Scalable Vector Graphics — an XML-based format that defines images using drawing instructions (primitives like shapes) instead of pixels. | Inline SVGs are part of the DOM → fully stylable and manipulable with CSS & JavaScript. |
| **Why Use SVG?**        | Infinite scalability without pixelation, crisp at any size/resolution, small file size for simple graphics, accessible, and dynamic. | Best used **inline** in HTML for maximum power (not just as `<img>`). |
| **Embedding**           | `<svg width="..." height="..."> ...shapes... </svg>`                        | Can be placed directly in HTML like any other element. |

### SVG Coordinate System & Sizing

| Attribute       | Description                                                                 | Example |
|-----------------|-----------------------------------------------------------------------------|---------|
| **width / height** | Controls the **rendered/display size** of the SVG (in px, %, etc.)         | `width="300" height="200"` or `width="100%"` |
| **viewBox**     | Defines the internal coordinate system: `"x y width height"` (min-x, min-y, width, height) | `viewBox="0 0 300 220"` |
| **Coordinate Origin** | (0,0) is at the **top-left** corner (y increases downward)                | Unlike CSS, no negative y for "up". |
| **Scaling**     | Use `viewBox` + percentage `width/height` for responsive, crisp scaling without recalculating coordinates. | Avoid hardcoding pixel values inside shapes when scaling. |

**ViewBox Tips**:
- First two numbers = panning/shifting the view.
- Last two numbers = zoom level (smaller values = zoom in).
- Decouples internal drawing coordinates from display size.

### Basic SVG Shapes

| Shape          | Element          | Key Attributes                                      | Simple Example |
|----------------|------------------|-----------------------------------------------------|---------------|
| **Circle**    | `<circle>`      | `cx` (center x), `cy` (center y), `r` (radius)     | `<circle cx="150" cy="110" r="60" />` |
| **Ellipse**   | `<ellipse>`     | `cx`, `cy`, `rx` (x-radius), `ry` (y-radius)       | `<ellipse cx="150" cy="150" rx="75" ry="50" />` |
| **Rectangle** | `<rect>`        | `x`, `y` (top-left), `width`, `height`, `rx`/`ry` (rounded corners) | `<rect x="60" y="100" width="180" height="100" rx="20" />` |
| **Line**      | `<line>`        | `x1 y1` (start), `x2 y2` (end)                      | `<line x1="80" y1="80" x2="200" y2="200" />` |
| **Polyline**  | `<polyline>`    | `points` (space/comma-separated x,y pairs)          | `<polyline points="60,100 100,180 140,140" />` |
| **Polygon**   | `<polygon>`     | `points` (auto-closes back to first point)          | `<polygon points="60,100 100,180 140,140 180,180 220,100" />` |
| **Path**      | `<path>`        | `d` (path data commands — complex shapes)           | (Advanced; covered in more detail in separate guides) |

### Styling Attributes (Presentational)

These can be set as **attributes** on SVG elements or as **CSS properties**.

| Attribute              | Description                                      | Common Values / Example |
|------------------------|--------------------------------------------------|-------------------------|
| **fill**              | Interior color of the shape                      | `"hotpink"`, `"none"`, `hsl(...)` |
| **stroke**            | Outline color                                    | `"oklch(0.9 0.3 164)"`, `"none"` |
| **stroke-width**      | Thickness of the outline                         | `5`, `10px` |
| **stroke-linecap**    | Style of line ends                               | `butt`, `round`, `square` |
| **stroke-linejoin**   | Style of corners where lines meet                | `miter`, `round`, `bevel` |
| **stroke-dasharray**  | Creates dashed/dotted lines                      | `"10, 20"` (dash 10px, gap 20px) |
| **stroke-dashoffset** | Shifts the starting point of dashes              | Useful for "drawing" effects (pre-animation) |

**Gotchas**:
- Stroke is centered on the edge (half inside, half outside the shape).
- Shapes disappear in degenerate cases (e.g., `r="0"`, `width="0"` or `height="0"` on rect).
- `rx`/`ry` on `<rect>` works like `border-radius` in CSS.

### Quick Usage Tips

- **Inline SVG** is recommended for interactivity and styling.
- SVG elements respond to CSS like HTML (e.g., `circle { fill: hotpink; transition: r 400ms; }`).
- JavaScript can dynamically change attributes (e.g., `element.setAttribute('r', '50')`).
- For responsive SVGs: Set `width="100%"` (or a container size) and a sensible `viewBox="0 0 W H"`.
- Combine shapes freely inside one `<svg>` element.
- Use tools or JS (e.g., trigonometry) to generate points for polygons dynamically.

**Example Full Inline SVG** (circle with stroke):
```html
<svg width="300" height="220" viewBox="0 0 300 220">
  <circle cx="150" cy="110" r="60" fill="none" stroke="#ffcc00" stroke-width="10" />
</svg>
```

