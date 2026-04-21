
### JavaScript Modules: `import` & `export` Cheat Sheet

| Feature                          | Syntax                                                                 | Description |
|----------------------------------|------------------------------------------------------------------------|-------------|
| **Named Export**                 | `export const name = "value";`<br>`export function func() {}`          | Export multiple things from a file by name |
| **Default Export**               | `export default function() {}`<br>`export default class MyClass {}`   | Only **one** default export per module |
| **Named Import**                 | `import { name, func } from "./module.js";`                            | Import specific named exports |
| **Default Import**               | `import MyDefault from "./module.js";`                                 | Import the default export (name can be anything) |
| **Import Everything**            | `import * as Module from "./module.js";`                               | Namespace import (all exports as an object) |
| **Alias (Rename)**               | `import { oldName as newName } from "./module.js";`                    | Rename imported item |
| **Export with Alias**            | `export { oldName as newName };`                                       | Rename when exporting |

### Common Import / Export Patterns

| Pattern                              | Code Example |
|--------------------------------------|--------------|
| **Named Exports + Named Imports**    | `export const PI = 3.14;`<br>`import { PI } from "./math.js";` |
| **Default Export + Default Import**  | `export default class User {}`<br>`import User from "./User.js";` |
| **Mix Default + Named**              | `export default class User {}<br>export const VERSION = "1.0";`<br>`import User, { VERSION } from "./User.js";` |
| **Namespace Import**                 | `import * as Utils from "./utils.js";`<br>`Utils.formatDate()` |
| **Re-export**                        | `export { func } from "./other.js";` |

### Important Rules

| Rule                                      | Details |
|-------------------------------------------|-------|
| **One default export per module**         | You can have only **one** `export default` per file |
| **File extension**                        | Usually `.js` (required in some bundlers/environments) |
| **Path**                                  | Use relative paths (`./`, `../`) or absolute paths |
| **Static imports**                        | `import` statements must be at the top level (not inside functions) |
| **Dynamic imports**                       | `import("./module.js")` – returns a Promise (covered later) |
| **Strict mode**                           | Modules are automatically in strict mode |

### Comparison Table: Named vs Default Exports

| Feature                    | Named Export                          | Default Export |
|----------------------------|---------------------------------------|----------------|
| Number per module          | Multiple allowed                      | Only one |
| Import syntax              | `import { name } from "..."`          | `import AnyName from "..."` |
| Best for                   | Utilities, constants, multiple functions | Main class or main function |
| Renaming                   | Required when importing               | Optional (you choose the name) |

### Practical Examples

```js
// math.js
export const PI = 3.14159;
export function square(x) { return x * x; }
export default function add(a, b) { return a + b; }

// main.js
import add, { PI, square as sq } from "./math.js";

console.log(add(5, 3));     // 8
console.log(PI);            // 3.14159
console.log(sq(4));         // 16
```

### Quick Reference Summary

| Need                                      | Use This |
|-------------------------------------------|----------|
| Export multiple things                    | Named exports (`export const`, `export function`) |
| Export main thing from a file             | Default export |
| Import specific things                    | Named imports `{ ... }` |
| Import main thing                         | Default import (no braces) |
| Import everything at once                 | Namespace import (`import * as ...`) |
| Rename something when importing           | `as` keyword |
