
### 1. Self-Hosted vs Hosted Fonts

| Approach          | Pros                                      | Cons                                      | When to Choose |
|-------------------|-------------------------------------------|-------------------------------------------|----------------|
| **Self-Hosted**   | Full control, no extra third-party connections, better caching, HTTP/2+ multiplexing | Requires manual optimization (subsetting, compression) | High-performance sites, full control needed |
| **Hosted Services** (Google Fonts, Adobe Fonts, etc.) | Easy setup, automatic updates, subsetting often built-in | Extra DNS/connection overhead, less control | Rapid prototyping, simpler projects |

**Recommendation**: Self-host when performance is critical; use hosted services for convenience.

### 2. Font Formats & Delivery

| Format   | Compression | Support      | Recommendation |
|----------|-------------|--------------|----------------|
| **WOFF2** | Excellent (best) | Modern browsers | Primary choice — always list first |
| **WOFF**  | Good        | Very wide    | Fallback for older browsers |
| Others (TTF, EOT, SVG) | Poor        | Limited      | Rarely needed today |

**Tip**: Serve only **WOFF2** unless you must support very old browsers.

### 3. Performance Mitigation Techniques

| Technique              | How It Helps                                      | Implementation Tips |
|------------------------|---------------------------------------------------|---------------------|
| **Subsetting**         | Dramatically reduces file size by removing unused glyphs | Use tools like `pyftsubset`, Font Squirrel, or glyphhanger. Combine with `unicode-range` in `@font-face`. |
| **unicode-range**      | Browser downloads only needed character subsets   | Example: `unicode-range: U+0020-007F;` (Basic Latin) |
| **Preload Critical Fonts** | Starts font download early (before CSS parsing)   | `<link rel="preload" href="font.woff2" as="font" type="font/woff2" crossorigin>` |
| **Preconnect**         | Reduces connection setup time for third-party hosts | `<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>` |
| **Variable Fonts**     | One file instead of multiple weights/styles       | Great when you need several weights; can be larger — test size |
| **Fewer Fonts Overall**| Reduces HTTP requests and total payload           | Prefer `system-ui` for body text; limit to 1–2 custom fonts |

### 4. Font Loading Strategies (FOIT / FOUT / FOFT)

| Strategy                  | Description                                      | Performance Impact | Best For |
|---------------------------|--------------------------------------------------|--------------------|----------|
| **FOIT** (Flash of Invisible Text) | Text hidden until font loads                     | Poor (delays readability) | Avoid |
| **FOUT** (Flash of Unstyled Text)  | Fallback font shown immediately, then swapped    | Good               | Most sites |
| **FOUT with Class**       | JS-controlled swap after fonts load              | Very good (grouped repaints) | Cloud-hosted fonts |
| **Critical FOFT**         | Load tiny subset (A–Z, a–z) first, then full font | Excellent (minimal CLS) | High-performance needs |

### 5. `font-display` Values (Most Important for Rendering)

| Value      | Block Period | Swap Period | Trade-offs | Recommended Use |
|------------|--------------|-------------|------------|-----------------|
| `auto`     | Browser default | Varies     | Inconsistent | Avoid |
| `block`    | ~2–3 seconds | Infinite   | Delays text rendering | When exact font is essential (logos) |
| `swap`     | 0ms          | Infinite   | Fast text, possible layout shift (CLS) | Most body text |
| `fallback` | ~100ms       | 3 seconds  | Good balance | Balanced performance |
| `optional` | ~100ms       | None       | Best performance, no CLS, may never swap | Performance-critical sites |

**Modern Recommendation**:
- Use **`font-display: swap`** for most cases.
- Use **`optional`** for maximum performance (no layout shift on slow connections).

### 6. Quick Code Examples

**Basic Optimized @font-face**
```css
@font-face {
  font-family: "MyFont";
  src: url("/fonts/myfont.woff2") format("woff2");
  font-display: swap;           /* or optional */
  unicode-range: U+0020-007F;   /* Basic Latin */
}
```

**Preload Critical Font**
```html
<link rel="preload" href="/fonts/myfont-regular.woff2" as="font" type="font/woff2" crossorigin>
```

**System Font Stack Fallback**
```css
body {
  font-family: "MyFont", system-ui, -apple-system, sans-serif;
}
```

### 7. Overall Best Practices Summary

- Always include a solid **font stack** with system fonts.
- Prioritize **performance** over perfect typography on first load.
- Subset aggressively and use `unicode-range`.
- Deliver critical fonts as early as possible (preload + inlining `@font-face` in `<head>`).
- Replace **icon fonts** with SVGs (better accessibility + no layout shifts).
- Test with Chrome DevTools (Network tab → Fonts) and Lighthouse (Core Web Vitals).
- Monitor **CLS** (Cumulative Layout Shift) caused by font swaps.

