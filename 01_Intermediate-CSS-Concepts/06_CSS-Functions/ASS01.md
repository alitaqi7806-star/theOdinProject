

### Transform Functions
Used primarily with the `transform` property for 2D/3D movements, rotations, scaling, and skewing.

| Function              | Description                                      | Common Syntax Example                          | Key Use Cases / Notes |
|-----------------------|--------------------------------------------------|------------------------------------------------|-----------------------|
| `translate()`         | Moves an element on the 2D plane                 | `transform: translate(30px, 50px);`            | x and y offsets |
| `translateX()`        | Moves horizontally                               | `transform: translateX(50px);`                 | — |
| `translateY()`        | Moves vertically                                 | `transform: translateY(20%);`                  | — |
| `translateZ()`        | Moves along the z-axis (3D)                      | `transform: translateZ(10px);`                 | Requires perspective |
| `translate3d()`       | Moves in 3D space                                | `transform: translate3d(10px, 20px, 30px);`    | x, y, z |
| `rotate()`            | Rotates around a fixed point (2D)                | `transform: rotate(45deg);`                    | — |
| `rotateX()` / `rotateY()` / `rotateZ()` | Rotates around an axis (3D)                   | `transform: rotateX(45deg);`                   | — |
| `rotate3d()`          | Rotates around a custom 3D axis                  | `transform: rotate3d(1, 1, 0, 45deg);`         | Axis vector + angle |
| `scale()`             | Scales on 2D plane                               | `transform: scale(1.5, 0.8);`                  | x and y factors |
| `scaleX()` / `scaleY()` / `scaleZ()` | Scales along one axis                         | `transform: scaleX(2);`                        | — |
| `scale3d()`           | Scales in 3D space                               | `transform: scale3d(1.2, 1.2, 1.2);`           | — |
| `skew()`              | Skews on 2D plane                                | `transform: skew(30deg, 20deg);`               | x and y angles |
| `skewX()` / `skewY()` | Skews along one axis                             | `transform: skewX(20deg);`                     | — |
| `matrix()`            | Applies a 2D transformation matrix               | `transform: matrix(1, 0.5, -0.5, 1, 0, 0);`    | Advanced |
| `matrix3d()`          | Applies a 3D transformation matrix               | `transform: matrix3d(...);`                    | Advanced |
| `perspective()`       | Sets 3D perspective distance                     | `transform: perspective(500px);`               | Creates depth |

### Math Functions
Allow calculations and dynamic values inside CSS properties.

| Function       | Description                                      | Common Syntax Example                          | Key Use Cases |
|----------------|--------------------------------------------------|------------------------------------------------|---------------|
| `calc()`       | Performs arithmetic calculations                 | `width: calc(100% - 20px);`                    | Responsive layouts, mixing units |
| `min()`        | Returns the smallest value from a list           | `font-size: min(16px, 4vw);`                   | Fluid typography |
| `max()`        | Returns the largest value from a list            | `width: max(300px, 50%);`                      | Fluid sizing |
| `clamp()`      | Clamps a value between min and max               | `font-size: clamp(1rem, 2.5vw, 2rem);`         | Perfect responsive text |
| `abs()`        | Returns the absolute value                       | `left: abs(-10px);`                            | — |
| `sign()`       | Returns the sign (-1, 0, or 1)                   | —                                              | — |
| `round()`      | Rounds a number (with strategy)                  | `width: round(10.6px);`                        | — |
| `mod()` / `rem()` | Modulo / remainder calculations               | `width: mod(10px, 3px);`                       | — |
| `pow()`        | Raises base to an exponent                       | `scale: pow(2, 3);`                            | — |
| `sqrt()`       | Square root                                      | `width: sqrt(25px);`                           | — |
| Trigonometric (`sin()`, `cos()`, `tan()`, `asin()`, `acos()`, `atan()`, `atan2()`) | Trigonometric & inverse functions | `transform: rotate(sin(30deg));`               | Advanced animations & shapes |

### Filter Functions
Used with the `filter` and `backdrop-filter` properties for visual effects.

| Function          | Description                                      | Common Syntax Example                     |
|-------------------|--------------------------------------------------|-------------------------------------------|
| `blur()`          | Applies Gaussian blur                            | `filter: blur(5px);`                      |
| `brightness()`    | Adjusts brightness                               | `filter: brightness(1.2);`                |
| `contrast()`      | Adjusts contrast                                 | `filter: contrast(150%);`                 |
| `drop-shadow()`   | Adds a shadow (like box-shadow but for image)    | `filter: drop-shadow(4px 4px 4px black);` |
| `grayscale()`     | Converts to grayscale                            | `filter: grayscale(100%);`                |
| `hue-rotate()`    | Rotates hue in HSL color space                   | `filter: hue-rotate(90deg);`              |
| `invert()`        | Inverts colors                                   | `filter: invert(80%);`                    |
| `opacity()`       | Adjusts opacity (similar to `opacity` property)  | `filter: opacity(0.5);`                   |
| `saturate()`      | Adjusts saturation                               | `filter: saturate(200%);`                 |
| `sepia()`         | Applies sepia tone                               | `filter: sepia(80%);`                     |

### Color Functions
For defining colors in modern formats.

| Function       | Description                                      | Common Syntax Example                          |
|----------------|--------------------------------------------------|------------------------------------------------|
| `rgb()` / `rgba()` | Red-Green-Blue (with optional alpha)          | `color: rgb(255 0 0 / 0.5);`                   |
| `hsl()` / `hsla()` | Hue-Saturation-Lightness                      | `color: hsl(200 100% 50% / 0.8);`              |
| `hwb()`        | Hue-Whiteness-Blackness                          | `color: hwb(200 20% 30%);`                     |
| `lab()` / `lch()` / `oklab()` / `oklch()` | Perceptually uniform color spaces (modern) | `color: oklch(70% 0.2 200);`                   |
| `color()`      | Specifies color in a given color space           | `color: color(srgb 1 0 0);`                    |

### Image & Gradient Functions
Used for backgrounds, borders, and content.

- `url()` — References an image or resource
- `linear-gradient()`, `radial-gradient()`, `conic-gradient()` — Create gradients
- `repeating-linear-gradient()`, `repeating-radial-gradient()`, `repeating-conic-gradient()`
- `image-set()` — Provides multiple image resolutions
- `cross-fade()` — Blends two images
- `element()` — Uses an HTML element as an image (experimental)

### Other Notable Functions
- **Counter functions**: `counter()`, `counters()`, `symbols()`
- **Shape functions**: `circle()`, `ellipse()`, `inset()`, `polygon()` (for `clip-path` and `shape-outside`)
- `attr()` — Retrieves an HTML attribute value
- `var()` — Uses custom properties (CSS variables)
- `env()` — Accesses environment variables (e.g., safe-area-inset)
- Easing functions: `cubic-bezier()`, `steps()`, `linear()`

### Quick Tips
- Most functions can be nested (e.g., `calc(100% - min(20px, 2vw))`).
- Many math functions are excellent for **fluid/responsive design** (especially `clamp()`, `min()`, `max()`).
