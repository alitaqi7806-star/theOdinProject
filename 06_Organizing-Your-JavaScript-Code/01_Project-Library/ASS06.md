
### Toggle Read Status – Complete Cheat Sheet

| Aspect                              | Recommendation & Best Practice |
|-------------------------------------|--------------------------------|
| **Goal**                            | Add a button on each book card that toggles the `read` status (`true` ↔ `false`) |
| **Best Approach**                   | Add a method directly to the `Book` prototype/class so every book instance can toggle itself |
| **Why a Prototype Method?**         | Keeps logic with the Book object (clean OOP design) and avoids repeating code |

### 1. Add Toggle Method to Book

**Using Class Syntax (Recommended):**

```js
class Book {
  constructor(title, author, pages, read) {
    this.id = crypto.randomUUID();
    this.title = title;
    this.author = author;
    this.pages = pages;
    this.read = read;           // boolean
  }

  // Prototype method to toggle read status
  toggleRead() {
    this.read = !this.read;     // Flip true <-> false
  }
}
```

**Using Constructor + Prototype (Alternative):**

```js
function Book(title, author, pages, read) {
  this.id = crypto.randomUUID();
  this.title = title;
  this.author = author;
  this.pages = pages;
  this.read = read;
}

// Add method to prototype
Book.prototype.toggleRead = function() {
  this.read = !this.read;
};
```

### 2. Update `displayBooks()` – Add Toggle Button

```js
function displayBooks() {
  const container = document.getElementById('library');
  container.innerHTML = '';

  myLibrary.forEach(book => {
    const card = document.createElement('div');
    card.classList.add('book-card');
    card.innerHTML = `
      <h3>${book.title}</h3>
      <p>by ${book.author}</p>
      <p>${book.pages} pages</p>
      <p class="read-status ${book.read ? 'read' : 'not-read'}">
        ${book.read ? '✅ Read' : '❌ Not Read'}
      </p>
      
      <button data-id="${book.id}" class="toggle-read-btn">
        ${book.read ? 'Mark as Unread' : 'Mark as Read'}
      </button>
      
      <button data-id="${book.id}" class="remove-btn">Remove</button>
    `;
    container.appendChild(card);
  });
}
```

### 3. Handle Toggle Click (Event Delegation)

```js
document.getElementById('library').addEventListener('click', (e) => {
  const bookId = e.target.dataset.id;

  if (e.target.classList.contains('toggle-read-btn')) {
    // Find the book and toggle its status
    const book = myLibrary.find(b => b.id === bookId);
    if (book) {
      book.toggleRead();        // Use the prototype method
      displayBooks();           // Re-render to show updated status
    }
  }

  if (e.target.classList.contains('remove-btn')) {
    removeBook(bookId);
  }
});
```

### Summary Table: Toggle Read Flow

| Step | Action | Key Code |
|------|------|----------|
| 1    | Add `toggleRead()` method to Book | `this.read = !this.read;` |
| 2    | Show Toggle button in each card | `<button data-id="..." class="toggle-read-btn">` |
| 3    | Detect click on toggle button | Event delegation using `classList.contains()` |
| 4    | Find book by ID | `myLibrary.find(b => b.id === bookId)` |
| 5    | Toggle status | `book.toggleRead()` |
| 6    | Refresh UI | `displayBooks()` |

### Bonus Tips

- Use the same event listener for both "Toggle Read" and "Remove" buttons (event delegation is efficient).
- Update button text dynamically based on current `read` status.
- Consider adding a CSS class (`read` / `not-read`) to visually style the status differently.
- Keep the method on the prototype so every book instance automatically has `.toggleRead()`.
