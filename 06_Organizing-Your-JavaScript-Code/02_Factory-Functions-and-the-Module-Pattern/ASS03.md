

### JavaScript Closures – MDN Cheat Sheet

| Concept                        | Definition                                                                 | Key Details |
|--------------------------------|----------------------------------------------------------------------------|-------------|
| **Closure**                    | A function that remembers the variables from its lexical scope even after the outer function has finished executing | The function "closes over" its surrounding state |
| **Lexical Scope**              | The scope in which a function was **declared** (not where it is called)   | Determines which variables the closure can access |
| **Closure Creation**           | Happens every time a function is created inside another function           | Inner function retains access to outer variables |
| **Why Closures Matter**        | Enable data privacy, state preservation, and functional programming patterns | One of the most powerful features in JavaScript |

### How Closures Work

| Step | What Happens |
|------|--------------|
| 1    | An outer function is executed |
| 2    | An inner function is defined inside the outer function |
| 3    | The inner function is returned (or passed elsewhere) |
| 4    | Even after the outer function finishes, the inner function retains access to the outer function’s variables |

### Classic Closure Examples

| Example                        | Code | Explanation |
|--------------------------------|------|-----------|
| **Basic Closure**              | `function outer() { let x = 10; return function inner() { console.log(x); } }` | `inner()` remembers `x` |
| **Counter**                    | `function createCounter() { let count = 0; return () => ++count; }` | Maintains private state |
| **Data Privacy**               | `function createUser(name) { return { getName: () => name }; }` | `name` is private |
| **Event Handler**              | `buttons.forEach(btn => btn.addEventListener('click', () => console.log(btn.id)))` | Remembers which button was clicked |

### Common Use Cases

| Use Case                        | Why Closure is Perfect |
|---------------------------------|------------------------|
| Creating private variables      | Variables are inaccessible from outside |
| Maintaining state in functions  | Counter, cache, configuration |
| Event listeners                 | Remembering element or data |
| Function factories              | Creating customized functions |
| Module Pattern                  | Simulating private members |

### Important Gotchas & Pitfalls

| Pitfall                              | Problem | Solution |
|--------------------------------------|--------|----------|
| **Loop with `var`**                  | All closures share the same variable | Use `let` or IIFE |
| **Using `this` inside closure**      | `this` may not be what you expect | Use arrow function or `.bind()` |
| **Memory leaks**                     | Closures can keep large objects in memory | Be careful with long-lived closures |
| **Performance**                      | Too many closures can impact memory | Usually not an issue in practice |

### Key MDN Takeaways

| Point | Summary |
|-------|---------|
| Closures are created automatically | Every time a function is nested inside another |
| Closures have access to the entire scope chain | They can access variables from outer functions and global scope |
| Closures are extremely common | Used in event handlers, callbacks, modules, and functional programming |
| `let` and `const` behave better with closures | They are block-scoped, reducing common bugs compared to `var` |
| Closures are not the same as objects | They provide true data privacy through lexical scoping |

### Quick Reference Table

| Question                              | Answer |
|---------------------------------------|--------|
| What is a closure?                    | A function + its lexical environment |
| When is a closure created?            | When an inner function is defined inside an outer function |
| Can closures modify outer variables?  | Yes — they hold a reference, not a copy |
| Are closures slow?                    | No — they are highly optimized by modern JavaScript engines |
| Should I avoid closures?              | No — they are a fundamental and powerful feature |

