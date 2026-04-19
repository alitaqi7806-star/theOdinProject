

### 1. Core Syntax / Operators

| Operator       | Description                          | Example                              | Expands To |
|----------------|--------------------------------------|--------------------------------------|------------|
| `>`            | Child element                        | `nav>ul>li`                          | `<nav><ul><li></li></ul></nav>` |
| `+`            | Sibling element                      | `div+p+bq`                           | `<div></div><p></p><blockquote></blockquote>` |
| `^`            | Climb up one level                   | `div+div>p>span+em^bq`               | `<div></div><div><p><span></span><em></em></p><blockquote></blockquote></div>` |
| `^^`           | Climb up two levels                  | `div+div>p>span+em^^bq`              | `<div></div><div><p><span></span><em></em></p></div><blockquote></blockquote>` |
| `()`           | Grouping                             | `div>(header>ul>li*2>a)+footer>p`    | Complex nested structure with header and footer |
| `*`            | Multiplication (repeat)              | `ul>li*5`                            | `<ul>` with 5 `<li>` elements |
| `$`            | Numbering (auto-increment)           | `ul>li.item$*5`                      | `<li class="item1">` to `<li class="item5">` |
| `$@n`          | Numbering starting from `n`          | `ul>li.item$@3*5`                    | Starts from 3 |
| `$@-`          | Numbering in reverse                 | `ul>li.item$@-*5`                    | Counts downward |
| `$$$`          | Numbering with leading zeros         | `ul>li.item$$$*5`                    | `item001`, `item002`, etc. |
| `{}`           | Text content                         | `a{Click me}`                        | `<a href="">Click me</a>` |
| `[]`           | Custom attributes                    | `td[rowspan=2 colspan=3]`            | `<td rowspan="2" colspan="3"></td>` |

### 2. HTML Abbreviations

| Abbreviation       | Description / Alias                  | Expands To |
|--------------------|--------------------------------------|------------|
| `!` or `html:5`    | HTML5 document boilerplate           | Full `<!DOCTYPE html>` + `<html>`, `<head>`, `<body>` |
| `doc`              | Basic HTML document                  | Similar to HTML5 boilerplate |
| `#id`              | ID attribute (implicit `<div>`)      | `<div id="id"></div>` |
| `.class`           | Class attribute (implicit `<div>`)   | `<div class="class"></div>` |
| `form#id.class`    | Combined ID + class                  | `<form id="id" class="class"></form>` |
| `a`                | Anchor link                          | `<a href=""></a>` |
| `a:link`           | Link with http protocol              | `<a href="http://"></a>` |
| `a:mail`           | Mailto link                          | `<a href="mailto:"></a>` |
| `img`              | Image                                | `<img src="" alt="">` |
| `link:css`         | Stylesheet link                      | `<link rel="stylesheet" href="style.css">` |
| `script:src`       | External script                      | `<script src=""></script>` |
| `input:text`       | Text input (alias `input:t`)         | `<input type="text">` |
| `input:password`   | Password input                       | `<input type="password">` |
| `input:email`      | Email input                          | `<input type="email">` |
| `btn`              | Button                               | `<button></button>` |
| `bq`               | Blockquote                           | `<blockquote></blockquote>` |
| `ul>li*5`          | Unordered list with 5 items          | `<ul><li></li>...</ul>` |
| `ol>li*5`          | Ordered list with 5 items            | `<ol><li></li>...</ol>` |
| `table>tr*3>td*4`  | Table with 3 rows and 4 columns      | Full table structure |
| `lorem`            | Lorem ipsum placeholder text         | Generates dummy text (e.g., `p>lorem` or `lorem10`) |

**Implicit Tags** (Emmet guesses the best tag):
- `.class` → `<div class="class"></div>`
- `ul>.item` → `<ul><li class="item"></li></ul>`
- `table>.row>.col` → `<table><tr class="row"><td class="col"></td></tr></table>`

### 3. CSS Abbreviations (Shorthand)

Emmet supports fuzzy matching in CSS files (e.g., `m20` → `margin: 20px;`).

| Category              | Abbreviation Examples                  | Expands To |
|-----------------------|----------------------------------------|------------|
| **Display**           | `d`, `d:n`, `dib`, `df`, `di`          | `display: block;`, `display: none;`, `display: inline-block;`, `display: flex;` |
| **Position**          | `pos`, `pos:a`, `pos:r`, `top`, `left` | `position: relative;`, `position: absolute;`, `top: ;` |
| **Margin / Padding**  | `m`, `mt`, `mr`, `mb`, `ml`, `p`, `pt` | `margin: ;`, `margin-top: ;`, `padding: ;` |
| **Dimensions**        | `w`, `h`, `minw`, `maxh`               | `width: ;`, `height: ;` |
| **Font**              | `f`, `fz`, `ff`, `fw`, `fs`            | `font: ;`, `font-size: ;`, `font-family: ;`, `font-weight: ;` |
| **Text**              | `ta`, `tac`, `tar`, `td`, `lh`         | `text-align: left;`, `text-align: center;`, `text-decoration: none;`, `line-height: ;` |
| **Background**        | `bg`, `bgc`, `bgi`                     | `background: ;`, `background-color: ;`, `background-image: ;` |
| **Color**             | `c`, `op`                              | `color: ;`, `opacity: ;` |
| **Border**            | `bd`, `bdrs`                           | `border: ;`, `border-radius: ;` |
| **Flexbox**           | `jc`, `ai`, `ac`                       | `justify-content: ;`, `align-items: ;`, `align-content: ;` |
| **Box Sizing**        | `bxz`                                  | `box-sizing: border-box;` |

**Common Value Shortcuts**:
- `m20` → `margin: 20px;`
- `p10-20` → `padding: 10px 20px;`
- `w100p` → `width: 100%;`
- `fz1.2e` → `font-size: 1.2em;`
- `c#fff` → `color: #fff;`

### Quick Tips
- Press **Tab** (or `Ctrl+E` in some editors) after typing the abbreviation to expand it.
- Works in HTML, CSS, SCSS, JSX, and many other file types.
- Combine freely: `div.container>(header>h1{Title})+main>(section*3>p{lorem})`
- Dummy text: `lorem`, `lorem5`, `lorem10`, etc.