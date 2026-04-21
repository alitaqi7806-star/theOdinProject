

### JavaScript Scope & Closures Cheat Sheet

| Concept                  | Definition                                                                 | Key Points & Examples |
|--------------------------|----------------------------------------------------------------------------|-----------------------|
| **Scope**                | The area of your code where a variable is accessible                       | Determines where you can use a variable |
| **Global Scope**         | Variables declared outside any function or block                           | Accessible everywhere (avoid polluting it) |
| **Function Scope**       | Variables declared inside a function with `var`, `let`, or `const`         | Only accessible inside that function |
| **Block Scope**          | Variables declared with `let` or `const` inside `{}` blocks                | `if`, `for`, `while`, etc. |
| **`var`**                | Function-scoped (or global)                                                | Can be hoisted and redeclared |
| **`let` / `const`**      | Block-scoped                                                           | Not hoisted, cannot be redeclared in same scope |

### Scope Types Comparison

| Scope Type         | Keyword     | Accessible Where?                          | Hoisted? | Can be Redeclared? | Best Practice |
|--------------------|-------------|--------------------------------------------|----------|--------------------|---------------|
| Global             | `var/let/const` | Everywhere                                 | Yes      | Yes (`var`)        | Avoid |
| Function           | `var`       | Inside the entire function                 | Yes      | Yes                | Rarely use |
| Block              | `let/const` | Only inside the `{}` block                 | No       | No                 | Preferred |

### What is a Closure?

| Concept                  | Explanation |
|--------------------------|-----------|
| **Closure**              | A function that remembers the variables from its lexical scope even after the outer function has finished executing |
| **Lexical Scope**        | The scope where the function was **defined** (not where it is called) |
| **Why Closures Matter**  | They allow data privacy, maintaining state, and creating factory functions |

### Classic Closure Examples

| Example Type               | Code Pattern |
|----------------------------|--------------|
| **Basic Closure**          | Outer function returns inner function that remembers variables |
| **Data Privacy**           | Create private variables that can’t be accessed from outside |
| **Counter**                | Maintain state between function calls |
| **Module Pattern**         | Create public API with private data |

### Common Closure Patterns

| Pattern                        | Use Case | Example |
|--------------------------------|----------|---------|
| **Factory Function**           | Create multiple similar functions | `function createGreeter(name) { return function() { console.log(`Hi ${name}`); } }` |
| **Private Variables**          | Data encapsulation | Variables only accessible via returned methods |
| **Event Listeners**            | Remembering element/data | Click handlers that remember which button was clicked |
| **setTimeout / Async**         | Preserving value in loops | `for` loop with `setTimeout` using closure |

### Key Takeaways from Wes Bos

| Topic                        | Important Insight |
|------------------------------|-------------------|
| **Scope Chain**              | JavaScript looks for variables from inner → outer scope until it finds it or reaches global |
| **Temporal Dead Zone**       | `let` and `const` are hoisted but not initialized (causes error if accessed early) |
| **Closure Memory**           | Closures keep references to outer variables alive even after outer function ends |
| **Performance**              | Closures are very efficient and widely used in real applications |
| **Common Gotcha**            | Using `var` in loops with async code creates unexpected behavior |

### Quick Reference Table

| Question                                 | Answer |
|------------------------------------------|--------|
| What is scope?                           | Where a variable is visible/accessible |
| What is a closure?                       | A function + its remembered lexical environment |
| When is a closure created?               | Every time a function is created inside another function |
| Can closures modify outer variables?     | Yes (they have reference, not copy) |
| Is `this` affected by closures?          | No — `this` is determined by how the function is called |
