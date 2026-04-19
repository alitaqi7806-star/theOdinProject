
### 1. Global Custom Properties (Defined on `:root`)

| Custom Property                  | Typical Value                          | Purpose / Usage Example |
|----------------------------------|----------------------------------------|-------------------------|
| `--color-primary`                | `#0066cc` or similar blue              | Main brand color for links, buttons, accents: `color: var(--color-primary);` |
| `--color-text`                   | `#222` (light) / `#eee` (dark)         | Body text color |
| `--color-background`             | `#ffffff` (light) / `#121212` (dark)   | Page background |
| `--color-surface`                | `#f8f9fa` (light) / `#1e1e1e` (dark)   | Cards, panels, containers |
| `--color-border`                 | `#ddd` (light) / `#333` (dark)         | Borders and dividers |
| `--color-success`                | Green shade                            | Success states, checkmarks |
| `--font-family-base`             | `system-ui, -apple-system, ...`        | Default font stack |
| `--font-size-base`               | `1rem`                                 | Base font size (used with `clamp()`) |
| `--font-size-lg`                 | `1.25rem` or `clamp(...)`              | Larger headings |
| `--spacing-xs`                   | `0.5rem`                               | Tiny gaps and padding |
| `--spacing-sm`                   | `1rem`                                 | Small spacing |
| `--spacing-md`                   | `1.5rem`                               | Standard spacing |
| `--spacing-lg`                   | `2.5rem`                               | Large sections |
| `--border-radius`                | `8px` or `0.5rem`                      | Buttons, cards, inputs |
| `--box-shadow`                   | `0 4px 12px rgba(0,0,0,0.1)`           | Subtle elevation for cards |

### 2. Component-Specific & Local Custom Properties

| Custom Property                  | Defined On                  | Purpose / Usage |
|----------------------------------|-----------------------------|-----------------|
| `--card-bg`                      | `.card` or similar          | Background for lesson/project cards: `background: var(--card-bg);` |
| `--button-bg`                    | `.btn` classes              | Button background color |
| `--button-text`                  | `.btn` classes              | Button text color |
| `--nav-bg`                       | `header` or `.navbar`       | Navigation bar background |
| `--accent-color`                 | Various interactive elements| Hover/focus states |
| `--link-color`                   | Links                       | Default link color (often same as `--color-primary`) |

### 3. Theming (Light / Dark Mode)

| Theme Mode     | Key Variables Overridden                          | How It's Applied |
|----------------|---------------------------------------------------|------------------|
| **Light Mode** (default) | `--color-text: #222; --color-background: #fff; --color-surface: #f8f9fa;` | Base `:root` values |
| **Dark Mode**  | `--color-text: #eee; --color-background: #121212; --color-surface: #1e1e1e; --color-border: #333;` | `.dark` class added to `<html>` or `:root` |

### 4. Common Usage Patterns on Odin Project

| Pattern                              | Example Code |
|--------------------------------------|--------------|
| **Typography**                       | `font-size: clamp(1.1rem, 2.5vw, 1.25rem);`<br>`color: var(--color-text);` |
| **Card Styling**                     | `.card { background: var(--color-surface); border-radius: var(--border-radius); box-shadow: var(--box-shadow); }` |
| **Button**                           | `.btn-primary { background: var(--color-primary); color: white; }` |
| **Spacing System**                   | `padding: var(--spacing-md);`<br>`gap: var(--spacing-sm);` |
| **Hover Effects**                    | `.card:hover { --accent-color: brighter-blue; }` (local override) |
| **Responsive**                       | Many sizes use `clamp()` combined with custom properties |

### 5. Key Takeaways from Inspecting Odin Project

- **Global-first approach** — Most variables live on `:root` for easy theming.
- **Semantic naming** — Variables use meaningful names like `--color-primary`, `--spacing-md` instead of abstract ones.
- **Component-friendly** — Local variables (e.g., on `.card`) allow overrides without affecting the whole page.
- **Modern techniques** — Combined with `clamp()`, `hsl()` color variations, and JavaScript-driven dark mode toggle.
- **Maintainability** — Changing one variable (e.g., `--color-primary`) updates buttons, links, accents across the entire site.

**How to Explore It Yourself**:
1. Open https://www.theodinproject.com/
2. Right-click → **Inspect** (or press F12)
3. Go to the **Elements** tab
4. Look at the `<html>` or `:root` styles — you'll see dozens of `--` variables
5. Click on various elements (cards, buttons, header) to see local overrides
