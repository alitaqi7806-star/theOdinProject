

### JavaScript Classes – Advanced Features Cheat Sheet (MDN)

| Feature                          | Syntax                                                                 | Description & Key Points |
|----------------------------------|------------------------------------------------------------------------|--------------------------|
| **Class Declaration**            | `class ClassName {}`                                                   | Basic class definition |
| **Constructor**                  | `constructor(params) {}`                                               | Runs when `new` is used. Initializes instance properties |
| **Extending Classes**            | `class Child extends Parent {}`                                        | Creates inheritance. Child class inherits from Parent |
| **super()**                      | `super(arguments)`                                                     | Calls the parent class constructor. Must be called before using `this` in child constructor |
| **Method Inheritance**           | Methods from parent are automatically available on child               | Child can override parent methods |
| **Private Properties**           | `#privateField = value;`                                               | Truly private (not accessible outside the class). Prefixed with `#` |
| **Private Methods**              | `#privateMethod() {}`                                                  | Can only be called from inside the class |
| **Static Properties**            | `static staticProp = value;`                                           | Belong to the class itself, not to instances |
| **Static Methods**               | `static staticMethod() {}`                                             | Called on the class: `ClassName.staticMethod()` |
| **Public vs Private**            | Public: normal names<br>Private: names starting with `#`               | Private fields/methods are not accessible from outside the class |

### Extending Classes (Inheritance)

| Feature                          | Example |
|----------------------------------|--------|
| **Basic Inheritance**            | ```js:disable-run
| **Overriding Methods**           | Child can redefine a method from the parent |
| **super keyword**                | Used to call parent constructor or parent methods |

### Private Properties & Methods

| Feature                          | Syntax | Accessibility |
|----------------------------------|--------|---------------|
| **Private Field**                | `#score = 0;` | Only accessible inside the class |
| **Private Method**               | `#calculateScore() {}` | Only callable from inside the class |
| **Public Field**                 | `score = 0;` | Accessible from outside |

### Static Properties & Methods

| Feature                          | Example |
|----------------------------------|---------|
| **Static Property**              | `static species = "Human";` |
| **Static Method**                | ```js<br>static fromJSON(data) {<br>  return new User(data.name);<br>}<br>``` |
| **Calling Static**               | `User.fromJSON(jsonData)` (called on the class, not instance) |

### Quick Comparison Table

| Feature                    | Belongs To          | Syntax Example                     | Accessible From Outside? |
|----------------------------|---------------------|------------------------------------|--------------------------|
| Normal Method              | Instance            | `greet() {}`                       | Yes |
| Static Method              | Class               | `static create() {}`               | Yes (via ClassName) |
| Private Field/Method       | Instance (hidden)   | `#score`, `#update()`              | No |
| Public Field               | Instance            | `score = 100`                      | Yes |

### Key Takeaways from MDN

- `extends` + `super()` is the standard way to create inheritance in modern JavaScript.
- Private fields/methods (`#`) provide true encapsulation (unlike the old `_underscore` convention).
- Static members are useful for utility functions and factory methods that belong to the class itself.
- You can mix public, private, and static members in the same class.
- Classes are primarily **syntactic sugar** over constructor functions + prototypes.

