

### 1. Basic vs Advanced Mindset

| Approach (Common "Waste")      | Better Approach (Kevin's Recommendation)                          | Benefit |
|--------------------------------|-------------------------------------------------------------------|---------|
| Everything declared in `:root` | Declare on specific elements or components when it makes sense    | Reduces repetition, improves readability |
| Using custom props only for colors/spacing | Use them to control entire groups of styles (e.g., themes per component) | One change updates multiple properties |
| Repeating long declarations    | Set a local custom property once and reference it with `var()`    | DRY code, easier maintenance |

### 2. Locally Scoped Custom Properties (The Big Win)

| Technique                        | Example Code                                                                 | Why It's Neat |
|----------------------------------|------------------------------------------------------------------------------|---------------|
| **Set once, use many times**     | `.card { --accent: #e74c3c; }`<br>`.card__title { color: var(--accent); }`<br>`.card__button { background: var(--accent); }` | Change `--accent` in one place → all related styles update |
| **Component-level theming**      | `.button { --btn-bg: blue; --btn-text: white; }`<br>`.button { background: var(--btn-bg); color: var(--btn-text); }` | Each component manages its own variables |
| **Contextual overrides**         | `.dark .card { --accent: #f39c12; }`                                         | Easy theming without rewriting everything |
| **No inheritance needed**        | Use `@property` with `inherits: false` for strict control                    | Prevents unwanted leaking to children |

### 3. Fallbacks & Undeclared Variables

| Technique                        | Example                                                                      | Use Case |
|----------------------------------|------------------------------------------------------------------------------|----------|
| **Simple fallback**              | `color: var(--accent, #3498db);`                                             | Safe default if variable isn't set |
| **Chained fallbacks**            | `color: var(--accent, var(--secondary, #95a5a6));`                           | Multiple layers of safety |
| **Undeclared variable trick**    | `background: var(--bg, hsl(200 50% 50%));`                                   | Define a sensible default directly in `var()` |
| **With HSL for flexibility**     | `--hue: 200;`<br>`background: hsl(var(--hue) 80% 60%);`                      | Change one value to shift entire color palette |

### 4. Creative & Powerful Patterns

| Pattern                              | Example                                                                      | Kevin's Insight |
|--------------------------------------|------------------------------------------------------------------------------|-----------------|
| **One variable controls many**       | `.hero { --main: #2c3e50; }`<br>`.hero h1, .hero p, .hero a { color: var(--main); }` | Reduces repetition dramatically |
| **Spacing / Layout control**         | `.container { --gap: 2rem; }`<br>`gap: var(--gap);`<br>`padding: var(--gap);`   | Easy to adjust spacing across a component |
| **State-based styling**              | `.card:hover { --accent: #27ae60; }`                                         | Hover, focus, or active states become cleaner |
| **Combining with `calc()` / `clamp()`** | `--size: clamp(1rem, 4vw, 2rem);`<br>`font-size: var(--size);`               | Super responsive with minimal code |
| **HSL color magic**                  | `--base-hue: 340;`<br>`color: hsl(var(--base-hue) 70% 50%);`                 | Quick theme variations by changing one number |

### 5. Registering Custom Properties (`@property`)

| Descriptor          | Example Value                  | Benefit |
|---------------------|--------------------------------|---------|
| `syntax`            | `'<color>'` or `'<length>'`    | Type checking & better error handling |
| `initial-value`     | `#3498db`                      | Automatic safe fallback |
| `inherits`          | `false`                        | Prevents inheritance (great for components) |

**Example:**
```css
@property --accent {
  syntax: '<color>';
  initial-value: #3498db;
  inherits: false;
}
```

### 6. Quick Tips from Kevin Powell

- Stop treating custom properties only as "global constants" — use them **locally** for maximum power.
- Set a custom property **once** near the element that needs it, then reference it with `var()` in child rules.
- Combine with modern tools: `clamp()`, `hsl()`, `calc()`, and JavaScript for dynamic updates.
- For theming (light/dark), override variables on a parent (e.g., `.dark { --accent: ... }`).
- Keep names meaningful: `--accent`, `--card-bg`, `--heading-color`, `--space-md`.
- Custom properties participate fully in the cascade and specificity — use them wisely.

This cheat sheet highlights the **"neat ways"** Kevin demonstrates: locally scoped variables, reducing repetition, component-level control, smart fallbacks, and creative combinations that make CSS more efficient and enjoyable.

**Main Video Referenced**: "Using CSS custom properties like this is a waste" (https://www.youtube.com/watch?v=_2LwjfYc1x8)  
Companion videos: "Master CSS Custom Properties" and "Get more out of custom properties".
