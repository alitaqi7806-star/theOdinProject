

### Remove Book from Library – Cheat Sheet

| Aspect                        | Recommendation & Best Practice |
|-------------------------------|--------------------------------|
| **Goal**                      | Add a "Remove" button to each book card that deletes the book from `myLibrary` array and updates the display |
| **Key Technique**             | Use **data attributes** (`data-id`) to link DOM elements to specific book objects |
| **Why `data-id`?**            | Each book has a unique `id` from `crypto.randomUUID()`. This is the safest and cleanest way to identify which book to remove |

### Step-by-Step Implementation

| Step | Task | Code / Details |
|------|------|----------------|
| **1** | Add Remove button in `displayBooks()` | Include a button with `data-id` attribute |
| **2** | Attach event listener               | Use **event delegation** on the parent container |
| **3** | Find and remove book                | Use `findIndex()` + `splice()` |
| **4** | Refresh display                     | Call `displayBooks()` after removal |

### Recommended Code

#### 1. Update `displayBooks()` to include Remove button

```js
function displayBooks() {
  const libraryContainer = document.getElementById('library');
  libraryContainer.innerHTML = '';

  myLibrary.forEach(book => {
    const bookCard = document.createElement('div');
    bookCard.classList.add('book-card');
    bookCard.innerHTML = `
      <h3>${book.title}</h3>
      <p>by ${book.author}</p>
      <p>${book.pages} pages</p>
      <p class="read-status">${book.read ? '✅ Read' : '❌ Not Read'}</p>
      
      <button data-id="${book.id}" class="toggle-read-btn">
        ${book.read ? 'Mark Unread' : 'Mark Read'}
      </button>
      
      <button data-id="${book.id}" class="remove-btn">Remove Book</button>
    `;
    libraryContainer.appendChild(bookCard);
  });
}
```

#### 2. Add Event Listener for Remove Buttons (Event Delegation)

```js
// Best placed after DOM is loaded
document.getElementById('library').addEventListener('click', (e) => {
  if (e.target.classList.contains('remove-btn')) {
    const bookId = e.target.dataset.id;           // Get the unique ID
    removeBook(bookId);
  }
});
```

#### 3. Create `removeBook()` Function

```js
function removeBook(bookId) {
  // Find the index of the book with matching id
  const index = myLibrary.findIndex(book => book.id === bookId);
  
  if (index !== -1) {
    myLibrary.splice(index, 1);     // Remove 1 item at that index
    displayBooks();                 // Re-render the library
  }
}
```

### Summary Table: Remove Book Flow

| Step | Action | Key Code |
|------|--------|----------|
| 1    | Render Remove button | `<button data-id="${book.id}" class="remove-btn">` |
| 2    | Click detection | Event delegation on parent container |
| 3    | Get book ID | `e.target.dataset.id` |
| 4    | Find book in array | `findIndex()` using `book.id` |
| 5    | Remove from array | `splice(index, 1)` |
| 6    | Update UI | `displayBooks()` |

### Important Tips

- Always use **event delegation** (`addEventListener` on the parent `#library` container) instead of adding listeners to each button individually.
- `data-id` must match the book's unique `id` created with `crypto.randomUUID()`.
- After removing, always call `displayBooks()` to refresh the UI.
- Never use array index for deletion — always use the unique `id`.
