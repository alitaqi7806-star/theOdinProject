

### Overview of the Assessment
- **Aim**: Test knowledge of type, class, ID, combinators, pseudo-classes, attribute selectors, and combining them.
- **Format**: Multiple small tasks (usually 4–5) with live editors.
- **Key Rule**: Use the most efficient and correct selector for each requirement.

### Task-by-Task Selector Cheat Sheet

| Task | Requirement                                                                 | Recommended Selector(s)                                      | Key Concept Tested                          |
|------|-----------------------------------------------------------------------------|--------------------------------------------------------------|---------------------------------------------|
| **Selectors 1** | Style basic elements, headings, lists, etc.                                 | `h2`, `ul`, `li`, `.intro`, etc.                             | Type selectors + simple class selectors     |
| **Selectors 2** | 1. Give the element with `id="special"` a yellow background<br>2. Give elements with class `alert` a 2px solid grey border<br>3. If an element has both `alert` and `stop` classes → red background<br>4. If an element has both `alert` and `go` classes → green background | `#special { background: yellow; }`<br>`.alert { border: 2px solid grey; }`<br>`.alert.stop { background: red; }`<br>`.alert.go { background: green; }` | ID selector, class selector, multiple classes on one element |
| **Selectors 3** | Target specific elements using combinators (descendant, child, sibling)     | `article p`, `section > p`, `h2 + p`, `h2 ~ p`               | Descendant (` `), Child (`>`), Adjacent (`+`), General sibling (`~`) |
| **Selectors 4** | Use structural pseudo-classes to style items by position                    | `:first-child`, `:last-child`, `:nth-child(odd/even)`, `:nth-of-type()` | Position-based pseudo-classes               |
| **Selectors 5** (Final / Advanced) | 1. Style links with specific attributes<br>2. Target elements with certain attribute values or patterns | `a[href]`, `a[href^="https"]`, `a[href$=".pdf"]`, `a[href*="contact"]`, `img[alt]` | Attribute selectors (`[attr]`, `^=`, `$=`, `*=`) |

### Most Common Selectors Tested in This Assessment

| Category                  | Selector Examples                                      | What It Does / When to Use |
|---------------------------|--------------------------------------------------------|----------------------------|
| **Basic**                 | `h1`, `.box`, `#header`                                | Type, class, ID            |
| **Multiple Classes**      | `.alert.stop`, `.alert.go`                             | Element with both classes  |
| **Combinators**           | `div p` (descendant)<br>`div > p` (child)<br>`h2 + p` (adjacent sibling)<br>`h2 ~ p` (general sibling) | Relationship between elements |
| **Pseudo-classes**        | `:first-child`, `:last-child`, `:nth-child(2n)`<br>`:only-child`, `:nth-of-type(3)` | Position or state among siblings |
| **Attribute Selectors**   | `[title]`<br>`[href="exact"]`<br>`[href^="https"]`<br>`[href$=".pdf"]`<br>`[class*="box"]` | Based on HTML attributes   |
| **Universal**             | `*`                                                    | Everything (use sparingly) |

### Quick Reference Table for Common Requirements

| What You Want to Target                          | Best Selector Example                     |
|--------------------------------------------------|-------------------------------------------|
| Element with specific ID                         | `#special`                                |
| Element with one class                           | `.alert`                                  |
| Element with two classes                         | `.alert.stop`                             |
| All paragraphs inside an article                 | `article p`                               |
| Direct child paragraphs                          | `article > p`                             |
| Paragraph right after a heading                  | `h2 + p`                                  |
| All paragraphs after a heading                   | `h2 ~ p`                                  |
| First item in a list                             | `li:first-child`                          |
| Even/odd rows                                    | `tr:nth-child(even)`                      |
| Link that starts with https                      | `a[href^="https"]`                        |
| Link that ends with .pdf                         | `a[href$=".pdf"]`                         |
| Any link containing "contact" in URL             | `a[href*="contact"]`                      |

### Tips for Completing the Assessment Successfully
- Always read the exact instruction for each sub-task.
- Use the **rightmost** part of the selector as the key selector (browsers read right to left).
- Prefer **class** and **attribute** selectors over deep descendant chains for better performance and specificity.
- Combine selectors wisely (e.g., `.alert.stop` instead of separate rules when possible).
- Test in the live editor — small typos in selectors are the most common mistake.

This cheat sheet covers the core selectors and patterns used in MDN's current **Test your skills: Selectors** assessment. It pairs perfectly with the previous topics (CSS Diner, Shay Howe's Complex Selectors article, and basic MDN selectors).

**Link to the assessment**:  
https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Styling_basics/Test_your_skills/Selectors

