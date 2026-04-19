
### 1. Common Selectors (Review)

| Selector Type     | Syntax Example          | Description                                      | Specificity / Notes                  |
|-------------------|-------------------------|--------------------------------------------------|--------------------------------------|
| Type              | `h1`                    | Selects all elements of that HTML tag            | Low (0-0-1)                          |
| Class             | `.tagline`              | Selects elements with the given class            | Medium (0-1-0)                       |
| ID                | `#intro`                | Selects the unique element with that ID          | High (1-0-0)                         |

### 2. Child & Descendant Selectors

| Selector Type          | Syntax Example              | Description                                                                 | Example Use Case                          |
|------------------------|-----------------------------|-----------------------------------------------------------------------------|-------------------------------------------|
| Descendant             | `article h2`                | All `h2` elements inside `article` (any nesting level)                      | Styling headings inside articles          |
| Direct Child           | `article > p`               | Only `p` elements that are **direct** children of `article`                 | Paragraphs directly inside article        |

### 3. Sibling Selectors

| Selector Type           | Syntax Example       | Description                                                                 | Example Use Case                          |
|-------------------------|----------------------|-----------------------------------------------------------------------------|-------------------------------------------|
| General Sibling         | `h2 ~ p`             | All `p` elements that follow an `h2` and share the same parent              | Paragraphs after headings                 |
| Adjacent Sibling        | `h2 + p`             | The `p` element that **immediately** follows an `h2` (same parent)          | First paragraph after a heading           |

### 4. Attribute Selectors

| Selector Type              | Syntax Example                        | Description                                                                 | Example HTML                              |
|----------------------------|---------------------------------------|-----------------------------------------------------------------------------|-------------------------------------------|
| Attribute Present          | `a[target]`                           | Any `<a>` with a `target` attribute (any value)                             | `<a target="_blank">`                     |
| Attribute Equals           | `a[href="http://google.com/"]`        | Exact match of attribute value                                              | `<a href="http://google.com/">`           |
| Attribute Begins With      | `a[href^="https://"]`                 | Value starts with the string                                                | `<a href="https://example.com">`          |
| Attribute Ends With        | `a[href$=".pdf"]`                     | Value ends with the string                                                  | `<a href="/file.pdf">`                    |
| Attribute Contains         | `a[href*="google"]`                   | Value contains the substring anywhere                                       | Any link with "google" in URL             |
| Attribute Spaced (Word)    | `a[rel~="tag"]`                       | Space-separated value contains the exact word                               | `<a rel="tag nofollow">`                  |
| Attribute Hyphenated       | `a[lang|="en"]`                       | Hyphen-separated value begins with the word (e.g., en-US, en-GB)            | `<a lang="en-US">`                        |

### 5. Pseudo-classes

Pseudo-classes style elements based on state, position, or structure. They start with a **single colon `:`**.

| Category                     | Syntax Examples                                      | Description                                                                 |
|------------------------------|------------------------------------------------------|-----------------------------------------------------------------------------|
| Link                         | `a:link`, `a:visited`                                | Unvisited vs visited links                                                  |
| User Action                  | `a:hover`, `a:active`, `a:focus`                     | Hover, active (click), focused (tab/click)                                  |
| UI State (Forms)             | `input:enabled`, `input:disabled`, `input:checked`, `input:indeterminate` | Enabled/disabled inputs, checked checkboxes/radios                          |
| Structural – Position        | `:first-child`, `:last-child`, `:only-child`         | First/last/only child of parent                                             |
| Structural – Of Type         | `:first-of-type`, `:last-of-type`, `:only-of-type`   | First/last/only of that element type among siblings                         |
| Structural – Nth             | `:nth-child(n)`, `:nth-last-child(n)`                | Nth child (supports numbers, `odd`, `even`, `2n+1`, etc.)                   |
| Structural – Nth of Type     | `:nth-of-type(n)`, `:nth-last-of-type(n)`            | Nth of that specific element type                                           |
| Other                        | `:target`, `:empty`, `:not(.awesome)`                | Target fragment, empty elements, negation                                   |

**Note**: `:nth-child()` and `:nth-of-type()` are very powerful and support formulas like `3n`, `2n+1`, `-n+5`.

### 6. Pseudo-elements

Pseudo-elements create or style parts of an element. Modern standard uses **double colon `::`**. (Shay Howe's article sometimes uses single colon `:`.)

| Type                        | Syntax Example                     | Description                                                                 | Common Use                              |
|-----------------------------|------------------------------------|-----------------------------------------------------------------------------|-----------------------------------------|
| First Letter                | `p::first-letter`                  | Styles the first letter of text                                             | Drop caps                               |
| First Line                  | `p::first-line`                    | Styles the first line of text                                               | Special formatting for opening lines    |
| Generated Content (Before)  | `div::before`                      | Inserts content before the element's content                                | Icons, quotes                           |
| Generated Content (After)   | `a::after`                         | Inserts content after the element's content                                 | Clearfix, icons                         |
| Selection                   | `::selection`                      | Styles text that the user has highlighted/selected                          | Custom highlight color                  |

### Quick Reference: Combinators

| Symbol | Name                    | Meaning                                      |
|--------|-------------------------|----------------------------------------------|
| (space)| Descendant              | Any descendant                               |
| `>`    | Direct Child            | Immediate child only                         |
| `+`    | Adjacent Sibling        | Immediately following sibling                |
| `~`    | General Sibling         | All following siblings                       |

### Best Practices from the Article
- Keep selectors as short as possible to improve performance and reduce specificity issues.
- Avoid over-qualifying selectors (e.g., `div.article p` when `.article p` is enough).
- Understand the **key selector** (rightmost part) — browsers evaluate selectors from right to left.
- Use classes and attribute selectors thoughtfully for maintainable code.

