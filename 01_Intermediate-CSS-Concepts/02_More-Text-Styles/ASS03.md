
### 1. Font Selection & Fallbacks

| Consideration              | Recommendation                                                                 | Why It Matters |
|----------------------------|--------------------------------------------------------------------------------|---------------|
| **Custom Fonts**           | Use `@font-face` with `local()` first, then `url()`                            | Prioritizes locally installed fonts for faster loading |
| **Font Stack**             | `font-family: "CustomFont", Helvetica, Arial, sans-serif;`                     | Provides reliable fallbacks if the custom font fails to load |
| **Generic Families**       | Always end with `serif`, `sans-serif`, `monospace`, etc.                       | Ensures basic readability when specific fonts are unavailable |
| **Variable Fonts**         | Prefer variable fonts when multiple weights/styles are needed                  | Reduces file size (one file instead of many) |
| **Number of Fonts**        | Limit to 1–2 custom fonts per project                                          | Improves performance and maintains visual consistency |

### 2. Font Sizing & Scaling

| Property / Technique       | Best Practice                                                                  | Tips |
|----------------------------|--------------------------------------------------------------------------------|------|
| **font-size**              | Use relative units: `rem`, `em`, or `clamp()` for fluid typography             | Avoid fixed `px` for body text to support user zoom |
| **Keywords**               | Prefer relative keywords (`smaller`, `larger`) over absolute (`xx-small`)      | Scales naturally with parent font-size |
| **Shorthand**              | Use `font` shorthand when setting multiple properties at once                  | Example: `font: 1rem/1.5 "MyFont", sans-serif;` |
| **Responsive Sizing**      | Combine `clamp(min, preferred, max)` or media queries                          | Creates smooth scaling across device sizes |

### 3. Line Length, Spacing & Readability

| Property                   | Recommended Value / Approach                                                   | Reasoning |
|----------------------------|--------------------------------------------------------------------------------|-----------|
| **Line Length (Measure)**  | ~45–75 characters per line (use `max-width` on text containers)                | Optimal for comfortable reading |
| **line-height**            | Unitless value (e.g., `1.5` or `1.6`)                                          | Scales better than `px` or `%`; improves readability |
| **letter-spacing**         | Subtle positive values only when needed (avoid overuse)                        | Too much reduces legibility |
| **word-spacing**           | Minimal adjustments; use sparingly                                             | Affects word rhythm |
| **Text Wrapping**          | `text-wrap: balance` for headings<br>`text-wrap: pretty` for paragraphs        | Creates visually balanced lines (modern CSS) |
| **Overflow Handling**      | `overflow-wrap: break-word` or `anywhere`<br>`word-break: break-all` (as last resort) | Prevents ugly horizontal overflow |

### 4. Accessibility & Internationalization

| Area                       | Best Practice                                                                  | Notes |
|----------------------------|--------------------------------------------------------------------------------|-------|
| **Contrast**               | Ensure sufficient color contrast between text and background                   | Critical for readability (test with tools) |
| **Logical Properties**     | Use `text-align: start/end` instead of `left/right`                            | Better support for RTL languages |
| **Direction**              | Set `direction: rtl` for right-to-left content (Arabic, Hebrew, etc.)          | Default is `ltr` |
| **Writing Mode**           | Use `writing-mode` and `text-orientation` carefully for vertical text          | Maintains legibility in non-Latin scripts |
| **Hierarchy**              | Clear visual hierarchy with size, weight, and spacing                          | Helps users scan content quickly |

### 5. Performance Considerations

| Technique                  | How to Implement                                                               | Benefit |
|----------------------------|--------------------------------------------------------------------------------|---------|
| **Font Loading**           | Set `font-display: swap` (or `optional`) in `@font-face`                       | Prevents invisible text (FOIT); shows fallback immediately |
| **Format**                 | Prioritize **WOFF2**; include WOFF as fallback                                 | Best compression |
| **Subsetting**             | Use `unicode-range` to load only needed characters                             | Smaller file sizes |
| **Preloading**             | `<link rel="preload" as="font">` for critical fonts                            | Starts download earlier |
| **Variable Fonts**         | Use when possible instead of multiple static files                             | Fewer requests and smaller total weight |
| **Limit Fonts**            | Avoid loading too many weights or styles                                       | Reduces HTTP requests and payload |

### 6. Additional Styling Features

| Feature                    | Property / Value                                                               | Use Case |
|----------------------------|--------------------------------------------------------------------------------|----------|
| **Text Decoration**        | `text-decoration` + sub-properties (color, thickness, style)                   | Links, emphasis |
| **Transformations**        | `text-transform: uppercase / lowercase / capitalize`                          | Without changing HTML |
| **Indentation**            | `text-indent`                                                                  | Paragraph first-line indent |
| **Truncation**             | `text-overflow: ellipsis` + `white-space: nowrap` + `overflow: hidden`         | Single-line truncation |
| **Pseudo-elements**        | `::first-letter`, `::first-line`, `::selection`                                | Decorative styling |
| **Advanced Control**       | `font-feature-settings`, `font-variation-settings`                             | OpenType features & variable font axes |

### Quick Modern Tips
- Start with a good system font stack for body text (`system-ui`).
- Use `rem` for most typography to respect user preferences.
- Test on real devices and with different zoom levels.
- Prioritize **readability** over fancy design — especially for long-form content.
- Combine with previous font performance practices (preload, subsetting, `font-display: swap`).

