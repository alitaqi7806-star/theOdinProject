
### JavaScript Classes – Cheat Sheet

| Concept                        | Syntax                                      | Description / Notes |
|--------------------------------|---------------------------------------------|---------------------|
| **Class Declaration**          | `class MyClass {}`                          | The modern way to define blueprints for objects |
| **Class Expression**           | `const MyClass = class {}`                  | Can be anonymous or assigned to a variable |
| **Constructor**                | `constructor() {}`                          | Special method that runs when you use `new` |
| **Methods**                    | `methodName() {}`                           | Regular methods added to the prototype |
| **Creating Instances**         | `const obj = new MyClass()`                 | Calls the constructor and creates a new object |
| **Class Fields (Properties)**  | `fieldName = value;`                        | Instance properties (declared directly in class body) |

### Detailed Class Structure

| Part                        | Example Code |
|-----------------------------|--------------|
| **Basic Class**             | ```js:disable-run
| **Class with Fields**       | ```js<br>class User {<br>  name = "Anonymous";   // public field<br>  age = 0;<br><br>  constructor(name) {<br>    this.name = name;<br>  }<br>}<br>``` |
| **Getter**                  | `get fullName() { return this.first + " " + this.last; }` |
| **Setter**                  | `set fullName(value) { [this.first, this.last] = value.split(" "); }` |
| **Static Method**           | `static createGuest() { return new User("Guest"); }` |

### Key Features Comparison

| Feature                        | Syntax                                      | Purpose |
|--------------------------------|---------------------------------------------|---------|
| **Constructor**                | `constructor(params) {}`                    | Initializes new objects |
| **Prototype Methods**          | `methodName() {}`                           | Shared methods (not duplicated per instance) |
| **Instance Fields**            | `field = value;` (inside class body)        | Properties on each instance |
| **Static Methods**             | `static methodName() {}`                    | Methods on the class itself (not on instances) |
| **Getters / Setters**          | `get prop() {}` / `set prop(value) {}`      | Computed or controlled properties |

### Important Rules & Gotchas

| Rule / Gotcha                        | Explanation |
|--------------------------------------|-----------|
| **No hoisting**                      | Classes are **not** hoisted (unlike function declarations) |
| **Strict mode**                      | Classes always run in strict mode |
| **Constructor is optional**          | If omitted, an empty constructor is created automatically |
| **Static vs Instance**               | `static` methods belong to the class, not to instances |
| **this in methods**                  | Inside regular methods, `this` refers to the instance |
| **new is required**                  | You must use `new` to create instances (`new User()`) |

### Common Patterns

| Pattern                            | Example |
|------------------------------------|---------|
| **Basic Class**                    | `class Rectangle { constructor(w, h) { this.width = w; this.height = h; } }` |
| **Class with Static Method**       | `static fromJSON(data) { return new User(data.name); }` |
| **Class with Getter**              | `get area() { return this.width * this.height; }` |
| **Extending another class**        | `class Admin extends User {}` (covered later) |

### Quick Reference Table

| Question                            | Answer |
|-------------------------------------|--------|
| How do you define a class?          | `class Name {}` |
| How do you create an object?        | `new ClassName()` |
| Where do methods go?                | Inside the class body (they go to `.prototype`) |
| How do you add instance properties? | In the constructor or as class fields |
| Are classes hoisted?                | No |
| Can you use getters/setters?        | Yes, with `get` and `set` keywords |

