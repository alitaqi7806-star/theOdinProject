
### 1. Length Units (`<length>`)

#### Absolute Length Units (Fixed size, best for print)

| Unit | Name                        | Equivalent                  | Common Use Cases                  | Example          | Notes |
|------|-----------------------------|-----------------------------|-----------------------------------|------------------|-------|
| `cm` | Centimeters                | 1cm ≈ 37.8px                | Print styles                      | `width: 5cm;`   | Rarely used on screens |
| `mm` | Millimeters                | 1mm = 1/10 cm               | Print styles                      | `margin: 10mm;` | Print-oriented |
| `Q`  | Quarter-millimeters        | 1Q = 1/40 cm                | Print & SVG                       | `font-size: 40Q;` | Obscure unit |
| `in` | Inches                     | 1in = 2.54cm = 96px         | Print styles                      | `width: 2in;`   | Varies by device |
| `pc` | Picas                      | 1pc = 1/6 in = 12pt         | Typography (print)                | `font-size: 12pc;` | 1pc = 12 points |
| `pt` | Points                     | 1pt = 1/72 in               | Typography (print)                | `font-size: 12pt;` | Common in print |
| `px` | Pixels                     | 1px = 1/96 in               | Screen layouts (most common)      | `padding: 16px;` | Most widely used; perceptual on high-DPI screens |

#### Relative Length Units (Scale with context)

| Unit | Name                              | Relative To                          | Common Use Cases                          | Example                  | Notes |
|------|-----------------------------------|--------------------------------------|-------------------------------------------|--------------------------|-------|
| `em` | Element font size                 | Current element's `font-size`        | Spacing, padding, typography              | `padding: 1.5em;`       | Compounds in nested elements |
| `rem` | Root element font size            | `<html>` element's `font-size`       | Consistent typography across the page     | `font-size: 1.25rem;`   | Preferred for scalability |
| `vw` | Viewport width                    | 1% of viewport width                 | Responsive full-width elements            | `width: 50vw;`          | Scales with browser resize |
| `vh` | Viewport height                   | 1% of viewport height                | Full-screen sections, hero banners        | `height: 100vh;`        | Useful for mobile |
| `vmin` | Viewport minimum                  | Smaller of `vw` or `vh`              | Responsive text/images                    | `font-size: 4vmin;`     | Good for scaling |
| `vmax` | Viewport maximum                  | Larger of `vw` or `vh`               | Responsive elements                       | `width: 80vmax;`        | - |
| `ch` | Character width                   | Width of "0" character               | Monospace typography, form fields         | `width: 40ch;`          | Great for text containers |
| `ex` | x-height                          | Height of lowercase "x"              | Typography (less common)                  | `line-height: 1ex;`     | Rarely used |
| `cap` | Capital letter height             | Height of capital "M"                | Typography                                | `font-size: 1cap;`      | Modern unit |
| `%`  | Percentage                        | Parent element's corresponding value | Fluid layouts, widths, heights            | `width: 50%;`           | Not accepted by all properties |

**Tip**: Use `rem` + `px` fallback for better accessibility and scalability.

### 2. Numeric Values

| Type              | Syntax                  | Description                              | Common Use Cases                  | Example             | Notes |
|-------------------|-------------------------|------------------------------------------|-----------------------------------|---------------------|-------|
| `<integer>`       | Whole number            | Positive or negative whole numbers       | Counters, grid spans              | `grid-column: 3;`  | No decimal |
| `<number>`        | Decimal number          | Can include fraction                     | Opacity, ratios, calculations     | `opacity: 0.75;`   | Unitless |
| `<dimension>`     | Number + unit           | Any number with a unit attached          | Most length/angle/time values     | `10px`, `45deg`    | Broad category |

### 3. Percentages (`<percentage>`)

- **Syntax**: `50%`, `100%`, `-25%`
- Represents a **fraction** of another value (usually parent's size or font-size).
- Common in: `width`, `height`, `padding`, `margin`, `font-size`.
- **Gotcha**: Not all properties accept `%` (e.g., `border-width` does not).

### 4. Color Values (`<color>`)

| Type              | Syntax Example                          | Description                                      | Notes |
|-------------------|-----------------------------------------|--------------------------------------------------|-------|
| Named colors      | `red`, `blue`, `rebeccapurple`          | Predefined keywords                              | Limited set |
| Hexadecimal       | `#ff00ff`, `#f0f`, `#ff00ff88`          | RGB in hex (6/3/8 digits)                        | Most common |
| RGB               | `rgb(255 0 255)`, `rgb(100% 0% 100%)`  | Red, Green, Blue (0–255 or %) + optional alpha   | Modern space-separated syntax |
| HSL               | `hsl(300 100% 50%)`                     | Hue, Saturation, Lightness + optional alpha      | Great for color manipulation |
| HWB               | `hwb(300 0% 0%)`                        | Hue, Whiteness, Blackness                        | Less common |
| Alpha             | `/ 0.5` or `/ 50%`                      | Transparency in modern functions                 | Affects only the color |

### 5. Other Common Units & Values

| Category       | Unit / Type          | Syntax          | Represents                          | Example                     | Notes |
|----------------|----------------------|-----------------|-------------------------------------|-----------------------------|-------|
| **Angles**     | `deg`                | `45deg`         | Degrees                             | `transform: rotate(45deg);` | Most common |
|                | `rad`                | `1.57rad`       | Radians                             | -                           | Math-based |
|                | `turn`               | `0.25turn`      | Full circle (1 turn = 360deg)       | -                           | Useful for animations |
| **Time**       | `s`                  | `2s`            | Seconds                             | `transition: 0.3s;`         | - |
|                | `ms`                 | `300ms`         | Milliseconds                        | `animation-duration: 500ms;` | More precise |
| **Resolution** | `dpi`                | `96dpi`         | Dots per inch                       | Print media queries         | Print & high-res screens |
|                | `dppx`               | `2dppx`         | Dots per pixel (device pixel ratio) | Media queries               | Modern |
| **Functions**  | `calc()`             | `calc(100% - 20px)` | Mathematical expressions            | `width: calc(50% + 10px);`  | Very powerful |
|                | `url()`              | `url("image.jpg")` | References to files/gradients       | `background-image: url(...);` | - |

### 6. Special Values & Keywords

- **Global keywords**: `inherit`, `initial`, `unset`, `revert`, `revert-layer`
- **Current color**: `currentColor` — inherits the element's `color` property
- **Transparent**: `transparent`
- **None**: `none` (removes value for many properties)
- **Auto**: `auto` (browser calculates value)

### Quick Tips
- Prefer **relative units** (`rem`, `%`, `vw/vh`) for responsive design.
- Use `px` for fine control and borders.
- `box-sizing: border-box;` makes `px` and percentages behave more predictably.
- Always test on different screen sizes and devices.
- Modern CSS supports **math functions** like `calc()`, `min()`, `max()`, `clamp()` for powerful responsive values.

