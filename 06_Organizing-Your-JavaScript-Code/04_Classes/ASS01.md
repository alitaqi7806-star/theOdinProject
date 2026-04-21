

### Getters and Setters in JavaScript – Cheat Sheet

| Concept                  | Definition                                                                 | Syntax Example |
|--------------------------|----------------------------------------------------------------------------|----------------|
| **Getter**               | A method that gets (retrieves) the value of a property                    | `get propertyName() {}` |
| **Setter**               | A method that sets (assigns) the value of a property                      | `set propertyName(value) {}` |
| **Purpose**              | Allow you to control how a property is accessed or modified                | Add validation, computation, or side effects |
| **Advantage**            | Makes objects behave like they have simple properties while running logic behind the scenes | Cleaner, safer code |

### Basic Syntax

| Type       | Syntax (Object Literal)                          | Syntax (Class) |
|------------|--------------------------------------------------|----------------|
| **Getter** | `get fullName() { return this.first + ' ' + this.last; }` | `get fullName() { ... }` |
| **Setter** | `set fullName(name) { ... }`                     | `set fullName(name) { ... }` |

### Real-World Examples

| Example                        | Code |
|--------------------------------|------|
| **Simple Getter**              | `get fullName() { return `${this.firstName} ${this.lastName}`; }` |
| **Simple Setter**              | `set fullName(name) { [this.firstName, this.lastName] = name.split(' '); }` |
| **Validation in Setter**       | `set age(value) { if (value < 0) throw new Error(); this._age = value; }` |
| **Computed Property**          | `get area() { return this.width * this.height; }` |

### Getters vs Setters Comparison

| Feature                    | Getter                                      | Setter |
|----------------------------|---------------------------------------------|--------|
| Triggered when             | Reading the property (`obj.prop`)           | Assigning to the property (`obj.prop = value`) |
| Can return a value         | Yes                                         | No (usually undefined) |
| Can perform validation     | Usually not                                 | Yes (very common) |
| Can have side effects      | Yes                                         | Yes |
| Can be used with classes   | Yes                                         | Yes |

### Using Getters and Setters in Classes

```js
class Circle {
  constructor(radius) {
    this._radius = radius;        // Private-like variable
  }

  // Getter
  get radius() {
    return this._radius;
  }

  // Setter with validation
  set radius(value) {
    if (value <= 0) throw new Error("Radius must be positive");
    this._radius = value;
  }

  // Computed getter
  get area() {
    return Math.PI * this._radius ** 2;
  }
}
```

### Common Patterns & Use Cases

| Use Case                        | Why Use Getter/Setter |
|---------------------------------|-----------------------|
| Data validation                 | Prevent invalid values (age, email, etc.) |
| Computed properties             | Derive values (fullName, area, totalPrice) |
| Internal state protection       | Hide private variables (`_radius`) |
| Logging or side effects         | Track when a property is accessed or changed |
| Backward compatibility          | Keep old property names while changing internal structure |

### Important Notes

| Note | Explanation |
|------|-----------|
| **No parentheses** | When using a getter: `obj.fullName` (not `obj.fullName()`) |
| **Private convention** | Prefix internal variables with `_` (e.g., `_radius`) to signal they should not be accessed directly |
| **Can be used in objects and classes** | Same syntax works in both |
| **Not truly private** | Getters/Setters are still part of the public API |

### Quick Summary Table

| Question                        | Answer |
|---------------------------------|--------|
| When do you use a getter?       | When you want to compute or return a value dynamically |
| When do you use a setter?       | When you want to control or validate a value being assigned |
| Can you have only a getter?     | Yes (read-only property) |
| Can you have only a setter?     | Yes (write-only property) |
| Do getters/setters work with classes? | Yes, with the same syntax |
