

### Overview

| Function     | Purpose                                      | Syntax                                      | Equivalent Logic                          | Best For |
|--------------|----------------------------------------------|---------------------------------------------|-------------------------------------------|----------|
| **`min()`**  | Returns the **smallest** value from a list   | `min(value1, value2, ...)`                  | Chooses the minimum                       | Setting a **maximum cap** on sizes (e.g., width won't exceed a fixed value) |
| **`max()`**  | Returns the **largest** value from a list    | `max(value1, value2, ...)`                  | Chooses the maximum                       | Setting a **minimum floor** on sizes (e.g., width won't go below a readable size) |
| **`clamp()`**| Restricts a value between **min** and **max**| `clamp(min, preferred, max)`                | `max(min, min(preferred, max))`           | **Fluid/responsive values** with both lower and upper bounds (ideal for typography) |

All three functions:
- Support mixed units (`px`, `rem`, `vw`, `%`, `em`, etc.) in one call.
- Allow math operations (`+`, `-`, `*`, `/`) directly (no need for `calc()` in most cases).
- Can be nested inside each other or other math functions.
- Are widely supported since July 2020 in all modern browsers.

### `min()` Function

| Aspect                  | Details |
|-------------------------|---------|
| **What it does**        | Selects the **smallest** computed value from the list |
| **Common Pattern**      | `property: min(relative-unit, fixed-unit);` → acts as a **maximum limit** |
| **Example 1**           | `width: min(50vw, 400px);`<br>→ Width scales with viewport but never exceeds 400px |
| **Example 2**           | `font-size: min(4vw, 2rem);` |
| **Multiple Values**     | `width: min(100vw, 800px, 90%);` |
| **With Math**           | `padding: min(10px + 2vw, 30px);` |

### `max()` Function

| Aspect                  | Details |
|-------------------------|---------|
| **What it does**        | Selects the **largest** computed value from the list |
| **Common Pattern**      | `property: max(relative-unit, fixed-unit);` → acts as a **minimum guarantee** |
| **Example 1**           | `width: max(30vw, 300px);`<br>→ Width grows with viewport but never below 300px |
| **Example 2**           | `font-size: max(1.2rem, 3vw);` → Ensures readable minimum text size |
| **Multiple Values**     | `font-size: max(1rem, 2vw, 1.5em);` |
| **With Math**           | `min-height: max(200px, 40vh);` |

### `clamp()` Function (Most Popular)

| Aspect                  | Details |
|-------------------------|---------|
| **What it does**        | Clamps the **preferred** value between a **minimum** and **maximum** bound |
| **Parameters**          | 1. Minimum value<br>2. Preferred (fluid) value<br>3. Maximum value |
| **Classic Fluid Typography** | `font-size: clamp(1rem, 2.5vw, 2.5rem);`<br>→ Starts at 1rem, grows with viewport, caps at 2.5rem |
| **Width Example**       | `width: clamp(200px, 50%, 600px);` |
| **With Math in Preferred** | `font-size: clamp(1rem, 1.5rem + 0.5vw, 3rem);` |
| **Nesting**             | `width: clamp(200px, min(80vw, 600px), 900px);` |

### Comparison Table: When to Use Each

| Goal                                      | Use This Function          | Example |
|-------------------------------------------|----------------------------|---------|
| Prevent element from getting **too wide** | `min()`                    | `width: min(90%, 1200px);` |
| Prevent element from getting **too small** | `max()`                   | `width: max(300px, 40vw);` |
| Fluid scaling **with both min & max**     | `clamp()`                  | `font-size: clamp(1rem, 4vw, 2.5rem);` |
| Minimum readable font size                | `max()` or `clamp()`       | `font-size: max(1rem, 2.5vw);` |
| Container that grows but stays readable   | `clamp()`                  | `max-width: clamp(300px, 80ch, 1200px);` |
| Responsive padding/margins                | `min()` / `clamp()`        | `padding: clamp(1rem, 3vw, 2rem);` |

### Practical Use Cases

| Use Case                        | Recommended Function | Example |
|---------------------------------|----------------------|---------|
| **Fluid Typography**            | `clamp()`            | `font-size: clamp(1rem, 2vw + 0.5rem, 2.5rem);` |
| **Card / Container Width**      | `min()` or `clamp()` | `width: min(100%, 600px);` |
| **Minimum Button / Input Size** | `max()`              | `min-width: max(120px, 20vw);` |
| **Hero Section Height**         | `clamp()`            | `min-height: clamp(300px, 50vh, 600px);` |
| **Responsive Spacing**          | `clamp()`            | `gap: clamp(1rem, 2vw, 3rem);` |

### Important Notes & Tips
- **Order matters in `clamp()`** — always: minimum, preferred, maximum.
- You can mix units freely (e.g., `px` + `vw` + `rem`).
- These functions work great inside `calc()`, but often you don't need `calc()` anymore.
- For accessibility: Always ensure text remains readable at 200% zoom (WCAG).
- Table layouts: Percentage-based values with these functions may sometimes resolve to `auto`.
- DevTools tip: In modern browsers, you can inspect the computed value to see which option was chosen.

This cheat sheet covers the in-depth behavior, syntax, real-world examples, and responsive power of `min()`, `max()`, and `clamp()` as detailed in the MDN pages.
