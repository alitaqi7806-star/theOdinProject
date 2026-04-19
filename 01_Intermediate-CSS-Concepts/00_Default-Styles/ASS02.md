
### Why Normalize or Reset Is Still Needed in 2023

Browsers ship with their own default stylesheets to ensure basic legibility and accessibility. However, these defaults vary across browsers, include undesirable behaviors (e.g., unexpected margins, small line-heights, `content-box` sizing), and often conflict with custom designs. This leads to "whack-a-mole" overrides. A normalize or reset creates a **predictable foundation**.

### Core Approaches Compared

| Approach              | Philosophy                                                                 | Key Characteristics                                                                 | Pros                                                                 | Cons                                                                 |
|-----------------------|----------------------------------------------------------------------------|-------------------------------------------------------------------------------------|----------------------------------------------------------------------|----------------------------------------------------------------------|
| **Normalize.css**     | Fix inconsistencies while **preserving useful browser defaults**           | Targets only styles that differ between browsers; keeps legibility & accessibility | Predictable cross-browser rendering; minimal changes; accessibility-friendly | Retains some annoying defaults (e.g., body margins, heading sizes)   |
| **Traditional Reset** (e.g., Eric Meyer's) | **Strip everything** to a true blank slate                                 | Sets margins, padding, borders, fonts, list styles, etc., to zero                   | Complete control; no surprises from browser defaults                 | Loses accessibility/legibility benefits; you must re-style everything |
| **Reboot / Preflight** (Bootstrap, Tailwind) | Hybrid: Normalize + **opinionated modern defaults**                        | Builds on normalize, adds `border-box`, responsive images, etc.                     | Clean, modern baseline; good defaults out of the box                 | More opinionated (may require overrides for your design)             |
| **Modern-Normalize**  | Updated normalize with contemporary fixes                                  | Modern version of Normalize.css; includes `border-box`, system font, form inheritance | Actively maintained; fixes real 2023 bugs (e.g., iOS text zoom)      | Still leaves some typography decisions to you                        |
| **Custom / Lightweight Reset** | Targeted fixes on top of normalize                                         | Small set of rules for margins, line-height, images, lists, etc.                    | Balanced; avoids overkill; easy to maintain                         | Requires manual curation                                             |

### Author's Recommended Stack (2023)

**modern-normalize** + a **very lightweight custom reset**.

**Why this combination?**
- `modern-normalize` handles browser consistency, bug fixes, and essential modern defaults (e.g., `box-sizing: border-box`, system-ui font, form inheritance).
- The lightweight reset removes remaining pain points (margins, heading styles, list bullets) without being overly aggressive.
- It keeps the stylesheet small, maintainable, and non-opinionated where it matters.

**Example Code (Recommended Lightweight Reset)**

```css
@import "modern-normalize";

:root {
  line-height: 1.5;                    /* Better readability than browser default ~1.15 */
}

h1, h2, h3, h4, h5, figure, p, ol, ul {
  margin: 0;
}

ol[role="list"], ul[role="list"] {
  list-style: none;
  padding-inline: 0;
}

h1, h2, h3, h4, h5 {
  font-size: inherit;
  font-weight: inherit;
}

img {
  display: block;
  max-inline-size: 100%;               /* Responsive images */
}
```

### Popular Modern Resets Mentioned in Context

| Reset / Tool                  | Style                          | Best For                                      | Notable Features |
|-------------------------------|--------------------------------|-----------------------------------------------|------------------|
| **modern-normalize**          | Normalize-focused              | Most projects without heavy frameworks        | `border-box`, system font, iOS fixes |
| **Josh Comeau's Custom Reset**| Hybrid (modern baseline)       | Developers wanting thoughtful defaults        | `margin: 0` on most elements, `text-wrap: pretty/balance`, font inheritance, reduced-motion support |
| **Tailwind Preflight**        | Opinionated hybrid             | Tailwind projects                             | Strong `border-box`, removes default styling aggressively but smartly |
| **The New CSS Reset** (Elad Shechter) | Minimal & modern               | Simple, clean starts                          | Focuses on common pain points with fewer rules |

### Key Takeaways & Advice

- **Normalize** is gentler and better for preserving accessibility/legibility.
- **Reset** gives maximum control but requires more work upfront.
- In 2023+, pure aggressive resets are less common; **hybrids** and **modern-normalize + targeted rules** win for most projects.
- Decide on your baseline **early** in the project — changing it later can be painful.
- Use the `revert` keyword when you want to restore browser defaults in specific contexts (e.g., long-form articles).
- If using a framework like Tailwind or Bootstrap, leverage its built-in Preflight/Reboot instead of adding your own.

**Final Recommendation from the Article**:  
Start with `modern-normalize` for consistency and bug fixes, then layer a small, opinionated reset only for the elements that consistently cause you pain (typography, spacing, images). This gives you a clean, accessible, and predictable starting point without overdoing it.

