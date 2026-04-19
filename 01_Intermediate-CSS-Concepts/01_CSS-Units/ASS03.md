

### Viewport Units Overview

| Unit   | Full Name                  | Definition                                      | Example                  | Scales Dynamically With |
|--------|----------------------------|-------------------------------------------------|--------------------------|-------------------------|
| `vw`   | Viewport Width             | 1% of the viewport's **width**                  | `width: 50vw;`           | Browser/window resize (width) |
| `vh`   | Viewport Height            | 1% of the viewport's **height**                 | `height: 100vh;`         | Browser/window resize (height) |
| `vmin` | Viewport Minimum           | 1% of the **smaller** dimension (width or height) | `font-size: 5vmin;`     | Smaller side of viewport |
| `vmax` | Viewport Maximum           | 1% of the **larger** dimension (width or height)  | `font-size: 8vmax;`     | Larger side of viewport |

**Key Behavior**: These units are truly responsive — they update live as the user resizes the browser or rotates their device.

### Common & Creative Use Cases

| Use Case                          | Recommended Units & Code Example                                      | Why It Works Well |
|-----------------------------------|-----------------------------------------------------------------------|-------------------|
| **Full-screen / Full-height sections** | `height: 100vh;` or `min-height: 100vh;`                             | Creates hero banners or app-like full-viewport experiences |
| **Sticky / Pinned Footer**        | `body { min-height: 100vh; }` + flexbox or grid                      | Footer stays at bottom until content pushes it down |
| **Responsive Hero Images**        | `max-height: 55vh;` or `max-height: 85vh;`                           | Prevents images from pushing content off-screen on tall viewports |
| **Fluid Typography**              | `font-size: 5vw;` or `font-size: calc(1rem + 2vw);`                 | Text scales smoothly with screen size (pair with `clamp()` for better control) |
| **Maintain Aspect Ratio**         | `width: 100vw; height: calc(100vw * (9/16));` (for 16:9)            | Creates responsive containers with fixed ratios (videos, images) |
| **Square Elements**               | `width: 50vw; height: 50vw;`                                         | Perfect squares that scale with viewport width |
| **Text Scaling Based on Smaller Dimension** | `font-size: 8vmin;`                                                 | Ensures text never gets too large on portrait mobile or too small on landscape |
| **Limiting Content Height**       | `max-height: 90vh; overflow: auto;`                                  | Keeps long content readable without scrolling the entire page off-screen |
| **Centering Content Vertically**  | `height: 100vh; display: flex; align-items: center;`                 | Simple full-viewport vertical centering |
| **Responsive Modals / Overlays**  | `top: 10vh; height: 80vh;`                                           | Modals that feel native to the current screen size |

### Tips & Gotchas from the Article

- **Mobile Browser Chrome Issue**: On mobile, `100vh` can include or exclude the address bar dynamically, causing layout jumps. Modern alternatives include `dvh` (dynamic viewport height), `svh` (small viewport height), and `lvh` (large viewport height) — though the original article predates widespread support.
- **Combine with `calc()`**: Viewport units shine when mixed with calculations, e.g., `height: calc(100vh - 80px);` for fixed headers.
- **Fluid + Readable Typography**: Use `vmin` or `clamp(1rem, 4vw, 2rem)` to avoid text becoming unreadable at extreme sizes.
- **Performance**: Viewport units are efficient and well-supported in all modern browsers.
- **Pair with Other Tools**: Great when combined with Flexbox/Grid for centering, or media queries as a fallback.

### Quick Demo Patterns

```css
/* Full viewport hero */
.hero {
  height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
}

/* Responsive square */
.square {
  width: 40vmin;
  height: 40vmin;
}

/* Fluid heading */
h1 {
  font-size: clamp(2rem, 8vw, 5rem);
}
```

This cheat sheet captures the fundamentals and the fun, creative techniques highlighted in the article (full-screen sections, aspect ratios, constrained images, fluid text, etc.).

Viewport units are especially powerful for immersive, device-agnostic designs. Practice by building a simple landing page with a `100vh` hero and fluid typography!

Let me know if you'd like code examples for any specific use case or a combined cheat sheet with other units (`px`, `rem`, `em`).