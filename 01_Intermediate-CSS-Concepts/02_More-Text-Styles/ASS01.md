
### 1. Why Use Web Fonts?

| Aspect                  | Explanation |
|-------------------------|-------------|
| **Purpose**             | Allow custom fonts beyond the limited "web-safe" fonts (e.g., Arial, Verdana, Georgia). |
| **Benefit**             | More creative and branded typography while ensuring consistent design across devices. |
| **Trade-off**           | Requires downloading font files (adds to page weight) and more testing for consistency. |
| **Alternatives**        | System font stacks (e.g., `system-ui`) or services like Google Fonts. |

### 2. Font Formats Comparison

| Format   | Full Name                     | Pros                                      | Cons                              | Best For                     |
|----------|-------------------------------|-------------------------------------------|-----------------------------------|------------------------------|
| **WOFF2** | Web Open Font Format 2       | Best compression, smallest size, modern features (variable fonts) | Limited support in very old browsers | Primary format (always list first) |
| **WOFF**  | Web Open Font Format 1       | Good compression, wide browser support (including IE9+) | Larger than WOFF2                | Fallback for broader compatibility |
| **TTF/OTF** | TrueType / OpenType         | Original desktop formats                  | Larger files, less optimized     | Legacy support               |
| **EOT**   | Embedded OpenType            | Old IE support                            | Outdated, rarely needed          | Very old Internet Explorer   |
| **SVG**   | SVG Fonts                    | Old mobile browser support                | Poor performance, deprecated     | Rarely used today            |

**Recommendation**: Always list **WOFF2 first**, then WOFF as fallback.

### 3. @font-face At-Rule (Core Syntax)

```css
@font-face {
  font-family: "MyCustomFont";           /* Required: name you will use */
  src: 
    url("fonts/myfont.woff2") format("woff2"),
    url("fonts/myfont.woff") format("woff");
  font-weight: normal;                   /* or 400, bold, 700, etc. */
  font-style: normal;                    /* or italic, oblique */
  font-display: swap;                    /* Controls loading behavior */
}
```

**Key Descriptors**

| Descriptor         | Values / Examples                          | Purpose |
|--------------------|--------------------------------------------|---------|
| `font-family`      | `"MyFontName"`                             | Name to reference in `font-family` property |
| `src`              | `url(...) format("woff2")`                 | Font file location(s) and format hints |
| `font-weight`      | `normal`, `bold`, `100`–`900`              | Defines which weight this file provides |
| `font-style`       | `normal`, `italic`, `oblique`              | Defines style variant |
| `font-display`     | `auto`, `block`, `swap`, `fallback`, `optional` | How text is displayed while font loads (swap is most popular) |
| `unicode-range`    | `U+0000-00FF`                              | Download only needed characters (saves bandwidth) |
| `font-stretch`     | `normal`, `condensed`, `expanded`          | For stretched/compressed variants |
| `font-variation-settings` | For variable fonts                      | Advanced control over axes |

### 4. Applying the Web Font

```css
body {
  font-family: "MyCustomFont", "Helvetica", "Arial", sans-serif;
}
```

**Font Stack Best Practice**:
- Custom web font first
- System/similar fonts as fallbacks
- Generic family last (`serif`, `sans-serif`, `monospace`)

### 5. Font Loading Strategies (`font-display`)

| Value      | Behavior                                                                 | Use Case |
|------------|--------------------------------------------------------------------------|----------|
| `swap`     | Show fallback font immediately, swap to web font when loaded             | Best for most text (recommended) |
| `block`    | Invisible text until web font loads (short timeout)                      | When exact font is critical |
| `fallback` | Short invisible period, then fallback forever if slow                    | Balanced performance |
| `optional` | May never swap if font loads too slowly                                  | Performance-critical sites |

### 6. Defining Multiple Weights & Styles

Define separate `@font-face` rules for each variant (or use one variable font file):

```css
@font-face {
  font-family: "MyFont";
  src: url("myfont-regular.woff2") format("woff2");
  font-weight: normal;
  font-style: normal;
}

@font-face {
  font-family: "MyFont";
  src: url("myfont-bold.woff2") format("woff2");
  font-weight: bold;
  font-style: normal;
}
```

Then simply use:
```css
h1 { font-weight: bold; }
```

### 7. Best Practices & Performance Tips

- Place all `@font-face` rules at the **top** of your CSS file.
- Use **WOFF2 + WOFF** for most projects.
- Host fonts on the **same domain** to avoid CORS issues.
- Use `unicode-range` to reduce file size.
- Prefer **Google Fonts** or similar services for quick setup (they handle hosting and `@font-face`).
- Always include a solid font stack with system fonts.
- Test across browsers and devices.
- Consider **variable fonts** for fewer files and more flexibility (one file for many weights/styles).
- Respect font licenses (many require attribution or payment).

### 8. Common Pitfalls

- Incorrect file paths in `url()`
- Forgetting fallback fonts → invisible or ugly text
- Loading too many font weights/styles
- Not setting `font-display: swap`
- Ignoring performance impact on Core Web Vitals

This cheat sheet covers everything in the MDN article, including the practical exercises (using Font Squirrel + Transfonter or Google Fonts). 

**Quick Start Tip**:  
Start with Google Fonts for learning, then move to self-hosted `@font-face` for full control.

