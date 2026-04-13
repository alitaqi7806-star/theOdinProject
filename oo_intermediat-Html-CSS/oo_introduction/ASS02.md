
### 1. Basics

| Topic                  | Syntax / Example                                                                 |
|------------------------|----------------------------------------------------------------------------------|
| **CSS Syntax**         | `selector { property: value; property2: value2; }`                              |
| **External CSS**       | `<link rel="stylesheet" type="text/css" href="style.css">`                      |
| **Internal CSS**       | `<style> div { color: #444; } </style>`                                          |
| **Inline CSS**         | `<tag style="property: value;">Content</tag>`                                    |
| **Box Model**          | **margin** → **border** → **padding** → **content**                             |
| **Clearfix**           | `.clearfix::after { content: ""; display: block; clear: both; }` (modern version) |

### 2. Selectors

| Selector Type              | Example                          | Description                                      |
|----------------------------|----------------------------------|--------------------------------------------------|
| Universal                  | `*`                              | All elements                                     |
| Element                    | `div`                            | All `<div>` tags                                 |
| Group                      | `div, p`                         | All divs and paragraphs                          |
| Descendant                 | `div p`                          | Paragraphs inside divs                           |
| Child                      | `div > p`                        | Direct child paragraphs                          |
| Adjacent Sibling           | `div + p`                        | Paragraph immediately after div                  |
| General Sibling            | `div ~ p`                        | All paragraphs after div                         |
| Class                      | `.classname`                     | Elements with that class                         |
| ID                         | `#idname`                        | Element with that ID                             |
| Combined                   | `div.classname`                  | Divs with specific class                         |

#### Pseudo-classes & Pseudo-elements

- `:hover`, `:active`, `:focus`, `:visited`, `:link`
- `:first-child`, `:last-child`, `:nth-child(n)`, `:nth-of-type(n)`
- `:only-child`, `:empty`, `:root`
- `::before`, `::after`, `::first-letter`, `::first-line`, `::selection`

#### Attribute Selectors

- `[attr]` — has attribute
- `[attr="value"]` — exact value
- `[attr~="value"]` — contains word
- `[attr^="value"]` — starts with
- `[attr$="value"]` — ends with
- `[attr*="value"]` — contains substring

### 3. Common CSS Properties (Grouped)

#### Layout & Positioning
| Property              | Common Values                          | Description |
|-----------------------|----------------------------------------|-----------|
| `display`             | `block`, `inline`, `inline-block`, `flex`, `grid`, `none` | How element is displayed |
| `position`            | `static`, `relative`, `absolute`, `fixed`, `sticky` | Positioning method |
| `top` / `right` / `bottom` / `left` | `10px`, `50%`, `auto` | Offset for positioned elements |
| `float`               | `left`, `right`, `none`                | Float element |
| `clear`               | `left`, `right`, `both`, `none`        | Clear floats |
| `z-index`             | `1`, `10`, `-1`, `auto`                | Stack order |
| `overflow`            | `visible`, `hidden`, `scroll`, `auto`  | Content overflow |

#### Box Model
| Property              | Common Values / Shorthand |
|-----------------------|---------------------------|
| `margin`              | `10px`, `20px 30px`, `10px 20px 30px 40px` |
| `padding`             | Same as margin |
| `border`              | `1px solid #000` |
| `border-radius`       | `10px`, `50%`, `10px 20px 30px 40px` |
| `box-sizing`          | `content-box`, `border-box` (recommended) |
| `width` / `height`    | `100px`, `50%`, `auto`, `fit-content` |
| `max-width` / `min-width` | `100%`, `1200px` |

#### Typography & Text
| Property                  | Common Values |
|---------------------------|---------------|
| `color`                   | `#333`, `rgb(255,0,0)`, `hsl(0,100%,50%)` |
| `font-family`             | `Arial, sans-serif`, `'Roboto', sans-serif` |
| `font-size`               | `16px`, `1.2rem`, `1em` |
| `font-weight`             | `400`, `700`, `bold` |
| `font-style`              | `normal`, `italic` |
| `line-height`             | `1.5`, `1.6em` |
| `text-align`              | `left`, `center`, `right`, `justify` |
| `text-decoration`         | `none`, `underline`, `line-through` |
| `text-transform`          | `uppercase`, `lowercase`, `capitalize` |
| `letter-spacing`          | `1px`, `0.5em` |
| `word-spacing`            | `2px` |

#### Background
| Property                  | Common Values |
|---------------------------|---------------|
| `background-color`        | `#fff`, `transparent` |
| `background-image`        | `url(image.jpg)` |
| `background-size`         | `cover`, `contain`, `100% 100%` |
| `background-position`     | `center`, `top left` |
| `background-repeat`       | `no-repeat`, `repeat-x`, `repeat-y` |
| `background` (shorthand)  | `color url() repeat position/size` |

#### Flexbox
| Property             | Common Values |
|----------------------|---------------|
| `display: flex`      | Enables flexbox |
| `flex-direction`     | `row`, `column`, `row-reverse`, `column-reverse` |
| `justify-content`    | `flex-start`, `center`, `space-between`, `space-around` |
| `align-items`        | `stretch`, `center`, `flex-start`, `flex-end` |
| `align-content`      | `flex-start`, `center`, `space-between` |
| `flex-wrap`          | `nowrap`, `wrap`, `wrap-reverse` |
| `flex` (shorthand)   | `1 1 auto` (grow, shrink, basis) |
| `align-self`         | Override align-items for single item |

#### CSS Grid
| Property                  | Common Values |
|---------------------------|---------------|
| `display: grid`           | Enables grid |
| `grid-template-columns`   | `repeat(3, 1fr)`, `200px 1fr 2fr` |
| `grid-template-rows`      | `auto 1fr` |
| `grid-gap` / `gap`        | `20px`, `10px 30px` |
| `justify-items`           | `start`, `center`, `end` |
| `align-items`             | `start`, `center`, `end` |
| `place-items`             | Shorthand for align + justify |
| `grid-column`             | `span 2` or `1 / 3` |
| `grid-row`                | `1 / 4` |

#### Animation & Transition
| Property                     | Common Values |
|------------------------------|---------------|
| `transition`                 | `all 0.3s ease` |
| `animation`                  | `name 2s ease infinite` |
| `animation-duration`         | `300ms`, `2s` |
| `animation-timing-function`  | `ease`, `linear`, `ease-in-out` |

#### Other Useful Properties
- `cursor: pointer`
- `opacity: 0.8`
- `box-shadow: 0 4px 10px rgba(0,0,0,0.2)`
- `filter: blur(5px)`, `grayscale(100%)`
- `transform: rotate(45deg)`, `scale(1.2)`, `translateX(50px)`

### 4. Media Queries (Responsive Design)

```css
@media (max-width: 768px) { ... }          /* Mobile */
@media (min-width: 1024px) { ... }         /* Desktop */
@media (prefers-color-scheme: dark) { ... } /* Dark mode */
```

**Common Breakpoints:**
- Mobile: ≤ 480px
- Tablet: 481px – 768px
- Desktop: ≥ 1024px

