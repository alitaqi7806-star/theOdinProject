

### Basics

| Aspect                        | Syntax / Example                                                                 | Description |
|-------------------------------|----------------------------------------------------------------------------------|-------------|
| **Declaring a Custom Property** | `--main-color: #3498db;`<br>`--spacing: 1.5rem;`                                 | Must start with `--`. Declared like any other property. |
| **Using a Custom Property**   | `color: var(--main-color);`<br>`padding: var(--spacing);`                        | Use the `var()` function to reference it. |
| **Global Scope (Recommended)** | `:root { --main-color: #3498db; }`                                               | Makes variables available to the entire document (highest in cascade). |
| **Local Scope**               | `.card { --card-bg: #f8f9fa; }`                                                  | Only available to the element and its descendants. |

### Fallbacks & Safety

| Feature                       | Example                                                                          | Description |
|-------------------------------|----------------------------------------------------------------------------------|-------------|
| **Basic Fallback**            | `color: var(--main-color, #ccc);`                                                | If `--main-color` is not defined, use `#ccc`. |
| **Multiple Fallbacks**        | `color: var(--main-color, var(--secondary-color, #ccc));`                        | Chain fallbacks. |
| **Invalid Value Handling**    | If variable is invalid, the whole declaration is ignored (unlike Sass).         | CSS variables are "live" — invalid values don't break everything. |

### Advanced & Practical Usage

| Topic                              | Example                                                                 | Why It's Powerful |
|------------------------------------|-------------------------------------------------------------------------|-------------------|
| **Theming (Light / Dark Mode)**    | `:root { --bg: #fff; --text: #333; }`<br>`.dark { --bg: #222; --text: #ddd; }` | Change one value → entire theme updates instantly. |
| **JavaScript Control**             | `document.documentElement.style.setProperty('--main-color', '#e74c3c');` | Dynamically update themes, user preferences, or interactive elements. |
| **Calculations**                   | `--gap: 1.5rem;`<br>`gap: calc(var(--gap) * 2);`                        | Combine with `calc()`, `clamp()`, `min()`, `max()`. |
| **Inheritance**                    | Variables declared on parent cascade down to children.                  | Powerful for component-level styling. |
| **Scoped Variables**               | `.button { --btn-color: blue; }` → only affects this button and children. | Prevents pollution of global namespace. |

### Common Real-World Patterns

| Pattern                            | Code Example |
|------------------------------------|--------------|
| **Color Palette**                  | `:root { --primary: #3498db; --primary-dark: #2980b9; --gray: #95a5a6; }` |
| **Spacing System**                 | `:root { --space-xs: 0.5rem; --space-sm: 1rem; --space-md: 1.5rem; --space-lg: 2.5rem; }` |
| **Typography Scale**               | `:root { --font-size-base: 1rem; --font-size-lg: 1.25rem; }` |
| **Responsive with Clamp**          | `--max-width: clamp(300px, 80%, 1200px);` |
| **Dark Mode Toggle**               | Add `.dark` class to `<html>` or `:root` and redefine variables. |

### Key Advantages Over Preprocessors (Sass/Less)

| Advantage                          | Explanation |
|------------------------------------|-------------|
| **Live / Dynamic**                 | Can be changed with JavaScript at runtime. |
| **Native**                         | No build step required. |
| **Cascade & Inheritance**          | Respect CSS cascade rules naturally. |
| **No Compilation**                 | Works directly in the browser. |
| **Fallbacks**                      | Built-in graceful degradation. |

### Important Notes from the Video
- Custom properties are **not** the same as Sass variables — they are real CSS and participate in the cascade.
- Always declare on `:root` for global use unless you specifically want local scoping.
- Names are case-sensitive (`--MainColor` ≠ `--main-color`).
- You can store almost any value: colors, lengths, numbers, strings, even complex values like shadows or gradients.
- Performance is excellent — browsers optimize them well.

This cheat sheet captures the core concepts, syntax, and practical patterns taught in the Web Dev Simplified introduction to CSS Custom Properties.

**Video**: Search for "CSS Variables Tutorial Web Dev Simplified" (or the 2019 version with the article link in the description).

