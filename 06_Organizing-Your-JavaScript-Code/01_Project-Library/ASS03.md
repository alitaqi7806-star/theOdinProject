

### Displaying Books from Array – Cheat Sheet

| Aspect                        | Recommendation & Best Practice |
|-------------------------------|--------------------------------|
| **Core Principle**            | **Separate Data from Display**<br>Keep book data in `myLibrary` array.<br>Use a dedicated function to render the UI from that data. |
| **Main Function**             | `displayBooks()` – loops through the array and creates DOM elements |
| **Data Structure**            | `myLibrary = []` – array of Book objects |
| **Rendering Strategy**        | Clear the container first, then loop and append new cards |

### Recommended Code Structure

| Part                          | Code / Implementation |
|-------------------------------|-----------------------|
| **Global Array**              | `let myLibrary = [];` |
| **Book Class**                | `class Book { constructor(title, author, pages, read) { ... } }` |
| **Display Function**          | `function displayBooks()` |
| **Container**                 | `<div id="library" class="book-grid"></div>` |

### `displayBooks()` Function Breakdown

```js
function displayBooks() {
  const libraryContainer = document.getElementById('library');
  libraryContainer.innerHTML = '';                 // Clear previous content

  myLibrary.forEach(book => {
    const bookCard = document.createElement('div');
    bookCard.classList.add('book-card');
    bookCard.innerHTML = `
      <h3>${book.title}</h3>
      <p>by ${book.author}</p>
      <p>${book.pages} pages</p>
      <p class="read-status">${book.read ? 'Read' : 'Not Read'}</p>
      <button data-id="${book.id}" class="toggle-read">Toggle Read</button>
      <button data-id="${book.id}" class="remove-book">Remove</button>
    `;
    libraryContainer.appendChild(bookCard);
  });
}
```

### Key Concepts & Best Practices

| Concept                          | Why It Matters |
|----------------------------------|----------------|
| **Separation of Concerns**       | Data (array) is separate from UI (DOM). This makes your code maintainable and scalable. |
| **Clear Before Render**          | Always do `container.innerHTML = ''` before looping to avoid duplicates |
| **Use `forEach`**                | Cleanest way to loop through the array and create elements |
| **Data Attributes**              | Use `data-id="${book.id}"` on buttons so you can identify which book to modify later |
| **Dynamic Content**              | Use template literals (`${}`) to insert book properties into HTML |
| **Reusability**                  | Call `displayBooks()` every time the library changes (add, remove, toggle read) |

### HTML Container Recommendation

```html
<div id="library" class="book-grid">
  <!-- Book cards will be dynamically added here -->
</div>
```

### Workflow Summary

1. User adds a book → `addBookToLibrary(...)`
2. Array gets updated
3. Call `displayBooks()` to refresh the UI
4. Repeat whenever data changes

### Common Mistakes to Avoid

- Manipulating DOM directly without using the array (breaks separation of concerns)
- Forgetting to clear the container before re-rendering (`innerHTML = ''`)
- Not using the book's unique `id` for delete/toggle buttons
- Rendering only once on page load instead of re-rendering after changes
