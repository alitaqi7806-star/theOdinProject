

### Book Constructor & Array Storage Cheat Sheet

| Topic                              | Details & Best Practice |
|------------------------------------|-------------------------|
| **Purpose**                        | Store all books in a single array called `myLibrary` |
| **Main Components**                | 1. Book Constructor<br>2. Function to add new books<br>3. Array to hold all books |
| **Unique ID**                      | Use `crypto.randomUUID()` for each book (recommended modern approach) |

### 1. Book Constructor

```js
function Book(title, author, pages, read) {
  this.id = crypto.randomUUID();     // Unique stable ID
  this.title = title;
  this.author = author;
  this.pages = pages;
  this.read = read;                  // boolean: true = read, false = not read
}
```

**Alternative (using class syntax - more modern):**

```js
class Book {
  constructor(title, author, pages, read) {
    this.id = crypto.randomUUID();
    this.title = title;
    this.author = author;
    this.pages = pages;
    this.read = read;
  }
}
```

### 2. Function to Add Books to Array

```js
let myLibrary = [];        // Main array that stores all books

function addBookToLibrary(title, author, pages, read) {
  const newBook = new Book(title, author, pages, read);
  myLibrary.push(newBook);
  return newBook;          // Optional: return the created book
}
```

### Complete Recommended Structure

| Item                        | Code / Recommendation |
|-----------------------------|-----------------------|
| **Global Array**            | `let myLibrary = [];` |
| **Book Constructor**        | Use `class Book` or constructor function with `crypto.randomUUID()` |
| **Add Book Function**       | Separate function (`addBookToLibrary`) that creates a book and pushes it to the array |
| **Unique Identifier**       | `this.id = crypto.randomUUID()` – Very important for later delete/edit functionality |
| **Properties**              | `id`, `title`, `author`, `pages`, `read` |

### Full Working Skeleton Example

```js
// Global array
let myLibrary = [];

// Book Constructor / Class
class Book {
  constructor(title, author, pages, read) {
    this.id = crypto.randomUUID();
    this.title = title;
    this.author = author;
    this.pages = pages;
    this.read = read;           // boolean
  }
}

// Function to add book
function addBookToLibrary(title, author, pages, read) {
  const book = new Book(title, author, pages, read);
  myLibrary.push(book);
  console.log(`Book added: ${book.title}`);
  return book;
}

// Example usage:
addBookToLibrary("The Hobbit", "J.R.R. Tolkien", 310, true);
addBookToLibrary("Dune", "Frank Herbert", 412, false);
```

### Key Points to Remember

| Point | Explanation |
|-------|-----------|
| **Why `crypto.randomUUID()`?** | Creates unique, stable IDs that won’t collide. Much better than using array index for deletion/editing. |
| **Separate function** | `addBookToLibrary()` should **not** be inside the constructor |
| **Array storage** | All books live in `myLibrary` array |
| **Read status** | Store as boolean (`true` / `false`) |
| **Future use** | The `id` will be critical when implementing delete and toggle read status |
