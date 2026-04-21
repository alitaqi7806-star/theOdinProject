

### Prototypes and Inheritance Cheat Sheet

| Concept                        | Definition                                                                 | Key Points / Example |
|--------------------------------|----------------------------------------------------------------------------|----------------------|
| **Prototype**                  | An object that other objects inherit properties and methods from           | Every JavaScript object has a hidden `[[Prototype]]` link |
| **`__proto__`**                | Old way to access an object's prototype (not recommended anymore)          | `obj.__proto__` → points to its prototype |
| **Prototype Chain**            | The chain of objects linked via prototypes until `null` is reached         | `obj → obj.__proto__ → obj.__proto__.__proto__ → null` |
| **Inheritance**                | When an object inherits properties/methods from its prototype              | Allows code reuse without duplication |
| **Constructor Function**       | A function used with `new` to create objects                               | `function Person() {}` |
| **`prototype` property**       | Every constructor function has a `.prototype` object                       | `Person.prototype` is shared by all instances |
| **`new` keyword**              | Creates a new object, sets its prototype, and calls the constructor        | `const john = new Person();` |

### How Prototypes Actually Work

| Step | What Happens When You Do `new Constructor()` |
|------|---------------------------------------------|
| 1    | A new empty object is created               |
| 2    | Its `[[Prototype]]` is set to `Constructor.prototype` |
| 3    | The constructor function runs with `this` bound to the new object |
| 4    | The new object is returned (unless constructor returns something else) |

### Important Relationships

| Relationship                              | Code Example |
|-------------------------------------------|--------------|
| Object → its prototype                    | `john.__proto__ === Person.prototype` |
| Constructor → its prototype               | `Person.prototype` |
| Prototype → its constructor               | `Person.prototype.constructor === Person` |
| End of prototype chain                    | `Object.prototype.__proto__ === null` |

### Prototypal Inheritance Examples

| Example | Code |
|---------|------|
| Basic Inheritance | `function Student(name) { this.name = name; }`<br>`Student.prototype = Object.create(Person.prototype);` |
| Method Inheritance | `Person.prototype.greet = function() { console.log("Hi"); }`<br>All instances of `Person` and `Student` can use `.greet()` |
| Property Lookup | When you do `john.greet()`, JavaScript first looks on `john`, then `john.__proto__`, then further up the chain |

### Key Takeaways from the Articles

| Topic | Summary |
|-------|---------|
| **Prototype Chain** | Property lookup continues up the chain until the property is found or `null` is reached |
| **Shared Methods** | Methods should be placed on the `.prototype` to avoid creating copies for every instance |
| **`__proto__`** | Only for reading/understanding. Never use it to set prototypes in real code |
| **Modern Alternatives** | We will learn `Object.create()` and `class` syntax soon (better than manual `__proto__`) |
| **Everything is an Object** | Even arrays and functions have prototypes (`Array.prototype`, `Function.prototype`) |

### Common Prototype Chain Visual

```
john (instance)
   ↓
Person.prototype
   ↓
Object.prototype
   ↓
null
```

### Quick Reference Table

| Term                    | Meaning |
|-------------------------|--------|
| `obj.__proto__`         | Link to the object's prototype (legacy) |
| `Constructor.prototype` | Object shared by all instances created by the constructor |
| `new`                   | Sets up the prototype link automatically |
| `Object.create(proto)`  | Modern way to create object with specific prototype |
| `instanceof`            | Checks if an object is in the prototype chain of a constructor |

