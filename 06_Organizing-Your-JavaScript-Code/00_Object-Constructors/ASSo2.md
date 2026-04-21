

### JavaScript `this` Keyword – Complete Cheat Sheet

| Context / Situation                          | Value of `this`                                      | Example | Key Pitfall / Warning |
|---------------------------------------------|------------------------------------------------------|--------|-----------------------|
| **Global Scope**                            | `window` (browser) or `global` (Node.js)             | `console.log(this);` | In strict mode = `undefined` |
| **Inside a Regular Function**               | `window` (non-strict) or `undefined` (strict mode)   | `function show() { console.log(this); }` | Most common source of bugs |
| **Inside a Method**                         | The object that owns the method                      | `obj.method()` → `this` = `obj` | Works as expected |
| **Constructor Function** (`new`)            | The newly created object instance                    | `new Person()` → `this` = new object | Safe and predictable |
| **Arrow Function**                          | Lexical `this` (inherits from surrounding scope)     | `() => console.log(this)` | Does **not** have its own `this` |
| **Event Listener** (addEventListener)       | The element that received the event                  | `btn.addEventListener('click', function() { ... })` | Common mistake: losing `this` |
| **Object Literal Method**                   | The object itself                                    | `{ sayHi() { console.log(this); } }` | Safe |
| **Callback inside method**                  | Usually `undefined` or `window`                      | `obj.method(function() { console.log(this); })` | Very common pitfall |

### Common Pitfalls & Solutions

| Pitfall                                      | Problem                                                                 | Best Solution |
|---------------------------------------------|-------------------------------------------------------------------------|---------------|
| **Losing `this` in callbacks**              | `this` becomes `undefined` or `window` inside nested functions         | Use arrow function or `.bind(this)` |
| **Using `this` in regular functions**       | `this` is not what you expect                                           | Prefer arrow functions for callbacks |
| **Strict mode vs Non-strict**               | In strict mode, global `this` = `undefined`                             | Always use strict mode (`"use strict";`) |
| **Arrow functions in methods**              | Arrow function does **not** get its own `this`**                        | Don’t use arrow functions as object methods if you need `this` |
| **Event handlers**                          | `this` refers to DOM element, not your object                           | Use arrow function or `bind()` |

### How to Control `this`

| Method               | Syntax Example                                           | When to Use |
|----------------------|----------------------------------------------------------|-------------|
| `.bind()`            | `obj.method.bind(obj)`                                   | When you need to permanently fix `this` |
| Arrow Function       | `() => { console.log(this) }`                            | Best for callbacks and preserving lexical `this` |
| `call()`             | `func.call(obj, arg1, arg2)`                             | One-time call with specific `this` |
| `apply()`            | `func.apply(obj, [arg1, arg2])`                          | One-time call with array of arguments |

### Real-World Examples

| Situation                                 | Code Example |
|-------------------------------------------|--------------|
| Safe method with arrow callback           | `obj.fetchData(() => { console.log(this.data); })` |
| Fixing `this` with bind                   | `button.addEventListener('click', this.handleClick.bind(this));` |
| Constructor with method                   | `function User(name) { this.name = name; }`<br>`User.prototype.sayHi = function() { console.log(this.name); }` |

### Key Takeaways

- `this` is **dynamic** — its value depends on **how** the function is called, not where it is written.
- Arrow functions do **not** have their own `this` — they inherit it lexically.
- The most common bug is losing `this` inside callbacks and event handlers.
- Always be explicit about `this` when working with objects and classes.
- In modern JavaScript, arrow functions + `.bind()` solve most `this` problems.

### Quick Reference Summary

- **Regular function** → `this` depends on call site
- **Arrow function** → `this` is lexical (from surrounding scope)
- **Method call** (`obj.method()`) → `this` = `obj`
- **`new Constructor()`** → `this` = new object
- **Event handler** → `this` = DOM element
