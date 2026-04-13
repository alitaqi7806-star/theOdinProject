
### Main Root
| Element     | Description                                      | Status     |
|-------------|--------------------------------------------------|------------|
| `<html>`    | Root element of an HTML document                 | No        |

### Document Metadata
| Element     | Description                                      | Status     |
|-------------|--------------------------------------------------|------------|
| `<base>`    | Specifies base URL for all relative URLs         | No        |
| `<head>`    | Container for document metadata                  | No        |
| `<link>`    | Links external resources (e.g., CSS, icons)      | No        |
| `<meta>`    | Generic metadata (charset, viewport, etc.)       | No        |
| `<style>`   | Embeds CSS styles                                | No        |
| `<title>`   | Document title (shown in browser tab)            | No        |

### Sectioning Root
| Element     | Description                                      | Status     |
|-------------|--------------------------------------------------|------------|
| `<body>`    | Visible content of the document                  | No        |

### Content Sectioning
| Element       | Description                                           | Status     |
|---------------|-------------------------------------------------------|------------|
| `<address>`   | Contact information                                   | No        |
| `<article>`   | Self-contained, reusable content (e.g., blog post)    | No        |
| `<aside>`     | Tangentially related content (e.g., sidebar)          | No        |
| `<footer>`    | Footer for nearest sectioning content                 | No        |
| `<header>`    | Introductory content or navigation                    | No        |
| `<h1>`–`<h6>` | Section headings (h1 highest level)                   | No        |
| `<hgroup>`    | Groups heading with subheadings/tagline               | No        |
| `<main>`      | Dominant/main content of the document                 | No        |
| `<nav>`       | Navigation links                                      | No        |
| `<section>`   | Generic thematic section (usually with heading)       | No        |
| `<search>`    | Container for search/filter controls                  | No        |

### Text Content
| Element       | Description                                           | Status     |
|---------------|-------------------------------------------------------|------------|
| `<blockquote>`| Extended quotation                                    | No        |
| `<dd>`        | Description/value in a description list               | No        |
| `<div>`       | Generic block-level container                         | No        |
| `<dl>`        | Description list                                      | No        |
| `<dt>`        | Term in a description list                            | No        |
| `<figcaption>`| Caption for a `<figure>`                              | No        |
| `<figure>`    | Self-contained content (often with caption)           | No        |
| `<hr>`        | Thematic break (horizontal rule)                      | No        |
| `<li>`        | List item                                             | No        |
| `<menu>`      | List of commands (similar to `<ul>`)                  | No        |
| `<ol>`        | Ordered list                                          | No        |
| `<p>`         | Paragraph                                             | No        |
| `<pre>`       | Preformatted text (preserves whitespace)              | No        |
| `<ul>`        | Unordered list                                        | No        |

### Inline Text Semantics
| Element     | Description                                           | Status     |
|-------------|-------------------------------------------------------|------------|
| `<a>`       | Hyperlink                                             | No        |
| `<abbr>`    | Abbreviation or acronym                               | No        |
| `<b>`       | Bring attention to text (no extra importance)         | No        |
| `<bdi>`     | Bidirectional isolate                                 | No        |
| `<bdo>`     | Bidirectional override                                | No        |
| `<br>`      | Line break                                            | No        |
| `<cite>`    | Title of a creative work                              | No        |
| `<code>`    | Computer code fragment                                | No        |
| `<data>`    | Machine-readable value                                | No        |
| `<dfn>`     | Defining instance of a term                           | No        |
| `<em>`      | Stress emphasis                                       | No        |
| `<i>`       | Idiomatic text (e.g., technical terms, thoughts)      | No        |
| `<kbd>`     | Keyboard/user input                                   | No        |
| `<mark>`    | Highlighted text                                      | No        |
| `<q>`       | Short inline quotation                                | No        |
| `<rp>`      | Ruby fallback parentheses                             | No        |
| `<rt>`      | Ruby text (pronunciation)                             | No        |
| `<ruby>`    | Ruby annotations for East Asian characters            | No        |
| `<s>`       | Strikethrough (no longer accurate)                    | No        |
| `<samp>`    | Sample output                                         | No        |
| `<small>`   | Side comments/small print                             | No        |
| `<span>`    | Generic inline container                              | No        |
| `<strong>`  | Strong importance                                     | No        |
| `<sub>`     | Subscript                                             | No        |
| `<sup>`     | Superscript                                           | No        |
| `<time>`    | Date/time with machine-readable `datetime` attribute  | No        |
| `<u>`       | Unarticulated annotation (underlined)                 | No        |
| `<var>`     | Variable in math/programming                          | No        |
| `<wbr>`     | Word break opportunity                                | No        |

### Image and Multimedia
| Element     | Description                                           | Status     |
|-------------|-------------------------------------------------------|------------|
| `<area>`    | Clickable area in an image map                        | No        |
| `<audio>`   | Sound content                                         | No        |
| `<img>`     | Image embedding                                       | No        |
| `<map>`     | Image map with areas                                  | No        |
| `<track>`   | Text tracks (subtitles, captions) for media           | No        |
| `<video>`   | Video content                                         | No        |

### Embedded Content
| Element        | Description                                           | Status     |
|----------------|-------------------------------------------------------|------------|
| `<embed>`      | External content (plugins)                            | No        |
| `<fencedframe>`| Nested browsing context with privacy features         | No        |
| `<iframe>`     | Nested browsing context (another HTML page)           | No        |
| `<object>`     | External resource (image, plugin, etc.)               | No        |
| `<picture>`    | Container for multiple image sources                  | No        |
| `<source>`     | Media resources for `<picture>`, `<audio>`, `<video>` | No        |

### SVG and MathML
| Element     | Description                                           | Status     |
|-------------|-------------------------------------------------------|------------|
| `<svg>`     | Container for SVG graphics                            | No        |
| `<math>`    | Root for MathML content                               | No        |

### Scripting
| Element       | Description                                           | Status     |
|---------------|-------------------------------------------------------|------------|
| `<canvas>`    | Graphics drawing area (Canvas/WebGL)                  | No        |
| `<noscript>`  | Fallback when scripting is disabled                   | No        |
| `<script>`    | Embedded or linked executable code (JS)               | No        |

### Demarcating Edits
| Element     | Description                                           | Status     |
|-------------|-------------------------------------------------------|------------|
| `<del>`     | Deleted text (with `cite` and `datetime`)             | No        |
| `<ins>`     | Inserted text                                         | No        |

### Table Content
| Element       | Description                                           | Status     |
|---------------|-------------------------------------------------------|------------|
| `<caption>`   | Table title/caption                                   | No        |
| `<col>`       | Column properties (inside `<colgroup>`)               | No        |
| `<colgroup>`  | Group of columns                                      | No        |
| `<table>`     | Tabular data                                          | No        |
| `<tbody>`     | Table body                                            | No        |
| `<td>`        | Table data cell                                       | No        |
| `<tfoot>`     | Table footer                                          | No        |
| `<th>`        | Table header cell                                     | No        |
| `<thead>`     | Table header group                                    | No        |
| `<tr>`        | Table row                                             | No        |

### Forms
Forms include many elements like `<form>`, `<input>` (with various types), `<label>`, `<button>`, `<fieldset>`, `<legend>`, `<select>`, `<option>`, `<optgroup>`, `<textarea>`, `<progress>`, `<meter>`, `<datalist>`, `<output>`, etc.  
→ Refer to the full MDN page for the complete list and input types.

### Interactive Elements
| Element       | Description                                           | Status     |
|---------------|-------------------------------------------------------|------------|
| `<details>`   | Collapsible disclosure widget                         | No        |
| `<dialog>`    | Modal dialog box                                      | No        |
| `<summary>`   | Summary/caption for `<details>`                       | No        |

### Web Components
| Element       | Description                                           | Status     |
|---------------|-------------------------------------------------------|------------|
| `<slot>`      | Placeholder in a Web Component template               | No        |
| `<template>`  | Template for reusable content (not rendered initially)| No        |

**Obsolete/Deprecated Elements** (do not use in modern HTML):  
Examples include `<acronym>`, `<applet>`, `<bgsound>`, `<big>`, `<center>`, `<dir>`, `<font>`, `<frame>`, `<frameset>`, `<marquee>`, `<menu> (in some contexts)`, `<nobr>`, `<noframes>`, `<param>`, `<plaintext>`, `<rb>`, `<rtc>`, `<strike>`, `<tt>`, `<xmp>`, and several others. Always check current status on MDN.

