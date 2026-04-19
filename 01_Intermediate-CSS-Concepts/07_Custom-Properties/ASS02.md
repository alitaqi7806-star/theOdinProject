

### 1. Inheritance of Custom Properties

| Concept                          | Details                                                                 | Example / Behavior |
|----------------------------------|-------------------------------------------------------------------------|--------------------|
| **Default Inheritance**          | Custom properties (`--*`) **always inherit** from their parent by default | Unlike most CSS properties, they cascade down to all descendants |
| **Inheritance Example**          | `.container { --box-color: teal; }` <br> `.two { }` → inherits `teal`   | Siblings and unrelated elements do **not** inherit |
| **Invalid Value Handling**       | Setting an invalid value on an element prevents inheritance for that element and its children | `.one { --box-color: invalid; }` → uses initial value, not parent's |
| **Key Difference**               | Value is resolved **at usage time** (`var()`), not stored globally      | Custom properties are **not** like Sass variables |

### 2. Controlling Inheritance with `@property`

| Descriptor       | Purpose                                      | Possible Values          | Effect |
|------------------|----------------------------------------------|--------------------------|--------|
| `inherits`       | Controls whether the custom property inherits | `true` (default) or `false` | `false` prevents inheritance from parent |
| `syntax`         | Defines the expected value type              | `<color>`, `<length>`, `<number>`, etc. | Enables type checking |
| `initial-value`  | Provides a default value                     | Any valid value matching syntax | Used when no value is set or value is invalid |

**Example:**
```css
@property --box-color {
  syntax: '<color>';
  initial-value: teal;
  inherits: false;
}
```

- With `inherits: false`, children do **not** get the parent's value.
- Useful for component libraries and Shadow DOM.

### 3. Fallback Values in `var()`

| Technique                     | Syntax Example                                              | Notes |
|-------------------------------|-------------------------------------------------------------|-------|
| **Simple Fallback**           | `color: var(--main-color, black);`                          | Second argument is used if variable is undefined or invalid |
| **Nested Fallback**           | `color: var(--main-color, var(--secondary-color, pink));`   | Chain multiple fallbacks |
| **Fallback with Commas**      | `font: var(--font-stack, "Helvetica", sans-serif);`         | Entire comma-separated list is treated as one fallback |
| **Using `@property` Initial** | Defined in `@property` → acts as automatic fallback         | Best for type safety |

### 4. Invalid Custom Property Values

| Situation                                 | Behavior of Custom Properties                              | Behavior of Regular CSS Properties |
|-------------------------------------------|------------------------------------------------------------|------------------------------------|
| Value is invalid for the target property  | Accepted during parsing, but becomes invalid when used     | Immediately discarded |
| Substitution into property                | If invalid → check if property is inheritable → use initial value or parent value | Previous valid declaration is kept |
| Mitigation Strategy                       | Use `@property` with `syntax` and `initial-value`          | Not available |

**Example of Invalid Value:**
```css
p {
  --text-color: 16px;        /* Looks fine as custom property */
  color: var(--text-color);  /* 16px is invalid for color → falls back to initial (black) */
}
```

### 5. Best Practices & Key Takeaways

| Topic                        | Recommendation |
|------------------------------|----------------|
| **Global vs Local**          | Declare on `:root` for global access. Use on specific elements for scoped variables. |
| **Type Safety**              | Use `@property` when you need strict syntax checking and controlled inheritance. |
| **Shadow DOM / Web Components** | Provide good fallbacks — variables do not pierce Shadow DOM boundaries by default. |
| **Performance**              | Avoid deeply nested `var()` fallbacks (slows down parsing). |
| **Naming**                   | Use clear, descriptive names (e.g. `--primary-color`, `--spacing-lg`). |
| **Limitations**              | Cannot use custom properties in selectors, media queries, or as property names. |
| **Cascading**                | Custom properties fully participate in the CSS cascade and specificity rules. |

### Quick Reference Summary

- **Inheritance** — On by default for `--` properties; controllable with `@property inherits: false`.
- **Fallbacks** — Second argument of `var()` or `initial-value` in `@property`.
- **Invalid Values** — Handled more leniently than regular properties; `@property` helps prevent surprises.
- **Power** — Enables theming, dynamic JavaScript control, and cleaner responsive designs.
