
### CSS Diner Complete Selector Cheat Sheet

| Level | Selector                          | Description / What it Selects                                      | Key Concept Taught                          |
|-------|-----------------------------------|--------------------------------------------------------------------|---------------------------------------------|
| 1     | `plate`                           | All plate elements                                                 | Type / Element Selector                     |
| 2     | `bento`                           | All bento elements                                                 | Type / Element Selector                     |
| 3     | `#fancy`                          | The element with id="fancy"                                        | ID Selector (`#`)                           |
| 4     | `plate apple`                     | All apples that are descendants of any plate                       | Descendant Selector (space)                 |
| 5     | `#fancy pickle`                   | All pickles that are descendants of the fancy plate                | ID + Descendant Selector                    |
| 6     | `.small`                          | All elements with class="small"                                    | Class Selector (`.`)                        |
| 7     | `orange.small`                    | All oranges that also have class="small"                           | Type + Class Selector                       |
| 8     | `bento orange.small`              | Small oranges that are descendants of bento                        | Class + Descendant Selector                 |
| 9     | `plate, bento`                    | All plates **and** all bentos                                      | Group Selector (comma)                      |
| 10    | `*`                               | **Everything** on the table                                        | Universal Selector (`*`)                    |
| 11    | `plate *`                         | All elements that are descendants of any plate                     | Universal + Descendant                      |
| 12    | `plate + apple`                   | Apples that are **immediately after** a plate (adjacent sibling)   | Adjacent Sibling Combinator (`+`)           |
| 13    | `bento ~ pickle`                  | All pickles that come **after** a bento (general sibling)          | General Sibling Combinator (`~`)            |
| 14    | `plate > apple`                   | Apples that are **direct children** of a plate                     | Child Combinator (`>`)                      |
| 15    | `orange:first-child`              | Oranges that are the first child of their parent                   | `:first-child` pseudo-class                 |
| 16    | `:only-child`                     | Elements that have no siblings (the only child)                    | `:only-child`                               |
| 17    | `:last-child`                     | Elements that are the last child of their parent                   | `:last-child`                               |
| 18    | `:nth-child(A)`                   | Elements at specific position A among siblings (e.g. 2, odd, even) | `:nth-child()`                              |
| 19    | `:nth-last-child(A)`              | Elements at position A when counting from the end                  | `:nth-last-child()`                         |
| 20    | `:first-of-type`                  | The first element of its type among siblings                       | `:first-of-type`                            |
| 21    | `:nth-of-type(A)`                 | The A-th element of its type among siblings                        | `:nth-of-type()`                            |
| 22    | `:nth-of-type(An+B)`              | Elements using formula (e.g. 2n+1 for every odd of that type)      | Advanced `:nth-of-type(An+B)`               |
| 23    | `:only-of-type`                   | The only element of its type in its parent                         | `:only-of-type`                             |
| 24    | `:last-of-type`                   | The last element of its type among siblings                        | `:last-of-type`                             |
| 25    | `:empty`                          | Elements with no children (and no text content)                    | `:empty` pseudo-class                       |
| 26    | `:not(X)`                         | All elements that do **not** match selector X                      | Negation pseudo-class `:not()`              |
| 27    | `[attribute]`                     | Elements that have the given attribute (any value)                 | Attribute Presence Selector                 |
| 28    | `A[attribute]`                    | Elements of type A that have the given attribute                   | Type + Attribute Selector                   |
| 29    | `[attribute="value"]`             | Elements where the attribute exactly equals "value"                | Exact Attribute Value Match                 |
| 30    | `[attribute^="value"]`            | Elements where the attribute **starts with** "value"               | Attribute Starts With (`^=`)                |
| 31    | `[attribute$="value"]`            | Elements where the attribute **ends with** "value"                 | Attribute Ends With (`$=`)                  |
| 32    | `[attribute*="value"]`            | Elements where the attribute **contains** "value" anywhere         | Attribute Contains (`*=`)                   |

### Quick Reference: CSS Selector Types

| Category              | Examples                              | Meaning |
|-----------------------|---------------------------------------|--------|
| **Basic**             | `plate`, `#fancy`, `.small`           | Type, ID, Class |
| **Combinators**       | `plate apple`, `plate > apple`, `plate + apple`, `bento ~ pickle` | Descendant, Child, Adjacent Sibling, General Sibling |
| **Grouping**          | `plate, bento`                        | Multiple selectors |
| **Universal**         | `*`, `plate *`                        | Everything |
| **Pseudo-classes**    | `:first-child`, `:last-child`, `:only-child`, `:nth-child(n)`, `:nth-last-child(n)` | Position among siblings |
| **Of-Type**           | `:first-of-type`, `:nth-of-type(n)`, `:only-of-type`, `:last-of-type` | Position by tag type |
| **Others**            | `:empty`, `:not(X)`                   | Empty or negation |
| **Attribute**         | `[title]`, `[title="value"]`, `[title^="val"]`, `[title$="ue"]`, `[title*="alu"]` | Based on attributes |

**Pro Tips from the Game:**
- Read the explanation on the right panel every time — it gives great examples.
- `:nth-child()` and `:nth-of-type()` are very powerful but count differently (all siblings vs same tag type).
- Attribute selectors are case-sensitive in most browsers.
- You can combine almost everything (e.g. `plate.small:first-child`).

This cheat sheet covers **all 32 levels** of CSS Diner. Use it for quick review after completing the game, or as a reference when you get stuck.

**Play the game here**: https://flukeout.github.io/

