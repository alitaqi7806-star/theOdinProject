

### CSS `opacity` Property Cheat Sheet

| Aspect                  | Details                                                                 |
|-------------------------|-------------------------------------------------------------------------|
| **Syntax**              | `opacity: <alpha-value>;`                                              |
| **Formal Definition**   | `opacity = <number> \| <percentage>`                                   |
| **Initial Value**       | `1`                                                                    |
| **Applies to**          | All elements                                                           |
| **Inherited**           | No                                                                     |
| **Computed Value**      | Clamped to the range `[0.0, 1.0]`                                      |
| **Animation Type**      | By computed value (smoothly animatable)                                |

### Values

| Value                  | Description                                      | Effect                                      |
|------------------------|--------------------------------------------------|---------------------------------------------|
| `0`                    | Fully transparent                                | Element is invisible                        |
| `0 < value < 1`        | Translucent                                      | Content behind the element is partially visible |
| `1` (default)          | Fully opaque                                     | Element is completely solid                 |
| `50%`                  | Equivalent to `0.5`                              | 50% opacity                                 |
| `0.75`                 | 75% opaque                                       | 25% transparency                            |
| `inherit`              | Takes the computed value from the parent         | —                                           |
| `initial`              | Sets to the initial value (`1`)                  | —                                           |
| `unset`                | Resets to inherited or initial value             | —                                           |

**Note**: Values outside the 0–1 / 0%–100% range are **clamped** (e.g., `-0.2` becomes `0`, `1.5` becomes `1`).

### Common Usage Examples

| Example                          | CSS Code                                              | Description |
|----------------------------------|-------------------------------------------------------|-----------|
| Fully Transparent                | `opacity: 0;`                                         | Element is hidden but still occupies space |
| Semi-Transparent                 | `opacity: 0.5;` <br> or <br> `opacity: 50%;`         | Half opacity |
| Hover Effect                     | `opacity: 1;`<br>`transition: opacity 0.3s;`<br>`&:hover { opacity: 0.7; }` | Smooth fade on hover |
| Fade Out Element                 | `opacity: 0;`                                         | Combined with transition for animations |
| Respect User Preference          | `@media (prefers-reduced-transparency) { opacity: 1; }` | Avoids transparency for accessibility |

### Important Behaviors & Notes

| Topic                        | Details |
|------------------------------|--------|
| **Affects**                  | The entire element **and all its children** as a group |
| **Stacking Context**         | Any `opacity` value other than `1` creates a new stacking context |
| **Not Inherited**            | Children keep their own opacity relative to the parent |
| **Background Only**          | Use `background-color: rgba(255, 255, 255, 0.5);` instead of `opacity` |
| **Pointer Events**           | Element with `opacity: 0` still receives clicks/focus by default |
| **Accessibility**            | Do **not** use `opacity: 0` to hide content from screen readers. Use `display: none`, `visibility: hidden`, or `aria-hidden="true"` instead. |
| **Contrast**                 | Reduced opacity can lower text contrast — ensure it meets WCAG ratios (4.5:1 normal text) |
| **Performance**              | Generally well-optimized and hardware-accelerated |

### Quick Reference Table (Most Used Values)

| Opacity Value | Visual Effect          | Use Case                     |
|---------------|------------------------|------------------------------|
| `1`           | Fully visible          | Default                      |
| `0.9`         | Very slight fade       | Subtle hover effects         |
| `0.75`        | Light transparency     | Overlays                     |
| `0.5`         | Medium transparency    | Disabled states, modals      |
| `0.25`        | Heavy transparency     | Background accents           |
| `0`           | Invisible              | Fade-out animations          |

**Pro Tip**: Combine with `transition: opacity 0.3s ease;` for smooth effects.

