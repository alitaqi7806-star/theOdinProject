
### Emmet Syntax (Core Operators)

| Abbreviation | Description                  | Example                  | Expands To |
|--------------|------------------------------|--------------------------|------------|
| `>`         | Child element               | `nav>ul>li`             | `<nav><ul><li></li></ul></nav>` |
| `+`         | Sibling element             | `div+p`                 | `<div></div><p></p>` |
| `^`         | Climb up one level          | `div>span^div`          | `<div><span></span></div><div></div>` |
| `()`        | Grouping                    | `(div>ul>li)*3`         | Three grouped structures |
| `*`         | Multiplication (repeat)     | `li*5`                  | Five `<li></li>` elements |
| `$`         | Numbering (with @ for start)| `li.item$*3`            | `<li class="item1">`, `<li class="item2">`, etc. |
| `{}`        | Text content                | `p{Hello World}`        | `<p>Hello World</p>` |
| `[]`        | Custom attributes           | `a[href="https://example.com"]` | `<a href="https://example.com"></a>` |
| `.`         | Class                       | `div.container`         | `<div class="container"></div>` |
| `#`         | ID                          | `div#header`            | `<div id="header"></div>` |

### Basic HTML Abbreviations & Implicit Tags

| Abbreviation | Expands To |
|--------------|------------|
| `!` or `html:5` | Full HTML5 boilerplate (`<!DOCTYPE html><html>...</html>`) |
| `div` or any tag | `<div></div>` (unknown tags become custom elements) |
| `.class` | `<div class="class"></div>` (implicit div) |
| `#id` | `<div id="id"></div>` (implicit div) |
| `ul>li*3` | Unordered list with 3 list items |
| `table>tr*2>td*3` | Table with 2 rows and 3 columns each |
| `img` | `<img src="" alt="">` |
| `a` | `<a href=""></a>` |
| `link:css` | `<link rel="stylesheet" href="style.css">` |
| `script:src` | `<script src=""></script>` |

### Form & Input Shortcuts

| Abbreviation | Expands To |
|--------------|------------|
| `form>input:text+input:password+button` | Form with text input, password input, and button |
| `input:email` | `<input type="email">` |
| `input:checkbox` | `<input type="checkbox">` |
| `btn` | `<button></button>` |
| `lbl` | `<label></label>` |

### CSS Abbreviations (Fuzzy Matching Supported)

Emmet in CSS mode uses shorthand with fuzzy search (e.g., `m20` works for margin). Units default to `px`; add `p` for `%`, `e` for `em`, etc.

| Category | Abbreviation Examples | Expands To |
|----------|-----------------------|------------|
| **Dimensions** | `w100`, `h50`, `m20`, `p10` | `width: 100px;`, `height: 50px;`, `margin: 20px;`, `padding: 10px;` |
| **Padding/Margin** | `mt20`, `ml-auto`, `p20-30` | `margin-top: 20px;`, `margin-left: auto;`, `padding: 20px 30px;` |
| **Display & Positioning** | `dib`, `df`, `pos:a`, `top0` | `display: inline-block;`, `display: flex;`, `position: absolute;`, `top: 0;` |
| **Text** | `tac`, `fz20`, `fwb`, `td:n` | `text-align: center;`, `font-size: 20px;`, `font-weight: bold;`, `text-decoration: none;` |
| **Colors & Background** | `c#fff`, `bgc#000`, `bd1-s#ccc` | `color: #fff;`, `background-color: #000;`, `border: 1px solid #ccc;` |
| **Flexbox/Grid** | `jc:c`, `ai:c`, `grid` | `justify-content: center;`, `align-items: center;`, `display: grid;` |
| **Vendor Prefixes** | `-bdrs` | `-webkit-border-radius: ; -moz-border-radius: ; border-radius: ;` |

### Advanced / Useful Combinations

- `nav>ul>li*5>a{Link $}` → Navigation with 5 numbered links.
- `div.container>(header>h1{Title})+ (main>section*3>p{lorem})` → Complex nested structure with dummy text.
- `lorem` or `lorem5` → Generates "Lorem ipsum..." placeholder text (5 words by default).
- `ol>li*3` → Ordered list with 3 items.

### Quick Tips
- **Dummy Text**: `p>lorem` or `p>lorem10` for paragraphs with placeholder content.
- **CSS Values**: `m1.5e` → `margin: 1.5em;`; `w50p` → `width: 50%;`.
- **Implicit Tags**: Many elements assume sensible parents (e.g., `li` inside `ul`).
- Works best in **VS Code** (built-in) or with the Emmet extension in other editors. Type abbreviation → **Tab** to expand.