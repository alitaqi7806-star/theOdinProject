
### New Book Form Implementation Cheat Sheet

| Aspect                          | Recommendation & Best Practice |
|---------------------------------|--------------------------------|
| **Goal**                        | Create a form that lets users add a new book to the `myLibrary` array |
| **Form Fields**                 | Title, Author, Pages, Read Status (checkbox), optional: ISBN, genre, etc. |
| **Display Method**              | You can use:<br>• A sidebar form<br>• A modal/dialog (`<dialog>` tag)<br>• A hidden form that appears on button click |
| **"New Book" Button**           | Should open/show the form |

### HTML Form Structure (Recommended)

```html
<dialog id="new-book-dialog">
  <form id="new-book-form">
    <h2>Add New Book</h2>
    
    <label for="title">Title:</label>
    <input type="text" id="title" required>

    <label for="author">Author:</label>
    <input type="text" id="author" required>

    <label for="pages">Number of Pages:</label>
    <input type="number" id="pages" min="1" required>

    <label for="read">Read?</label>
    <input type="checkbox" id="read">

    <button type="submit">Add Book</button>
    <button type="button" id="cancel-btn">Cancel</button>
  </form>
</dialog>
```

### JavaScript – Handling Form Submission

| Step | Code / Technique | Why It’s Important |
|------|------------------|--------------------|
| **1** | Select form and dialog | `const form = document.getElementById('new-book-form');` |
| **2** | Listen for submit event | `form.addEventListener('submit', handleSubmit);` |
| **3** | Use `event.preventDefault()` | **Critical**: Prevents the browser from trying to send the form to a server |
| **4** | Get form values | Use `FormData` or directly access `.value` |
| **5** | Create and add book | Call `addBookToLibrary(...)` |
| **6** | Refresh display | Call `displayBooks()` |
| **7** | Close the form/dialog | `dialog.close()` |

### Complete Submit Handler Example

```js
function handleSubmit(e) {
  e.preventDefault();                    // ← This stops default form submission

  const title = document.getElementById('title').value;
  const author = document.getElementById('author').value;
  const pages = parseInt(document.getElementById('pages').value);
  const read = document.getElementById('read').checked;

  addBookToLibrary(title, author, pages, read);
  displayBooks();

  // Reset and close form
  e.target.reset();
  document.getElementById('new-book-dialog').close();
}
```

### Key Points & Common Issues

| Issue / Concept                     | Solution |
|-------------------------------------|----------|
| Form submits and refreshes page     | Always use `e.preventDefault()` on submit |
| Form values not being captured      | Use `.value` or `FormData` API |
| Dialog not showing                  | Use `dialog.showModal()` (preferred) or `dialog.show()` |
| Need to cancel form                 | Add a Cancel button that calls `dialog.close()` |
| Clearing form after submit          | Call `form.reset()` after successful submission |

### Bonus: Opening the Form

```js
const newBookBtn = document.getElementById('new-book-btn');
const dialog = document.getElementById('new-book-dialog');

newBookBtn.addEventListener('click', () => {
  dialog.showModal();        // Modern way to show dialog
});
```

### Summary Checklist

- [ ] “New Book” button exists
- [ ] Form is properly structured with labels and inputs
- [ ] Form is inside a `<dialog>` or shown/hidden via JS
- [ ] Submit event listener is attached
- [ ] `e.preventDefault()` is used
- [ ] Form values are read correctly
- [ ] New book is added to `myLibrary` array
- [ ] `displayBooks()` is called after adding
- [ ] Form is reset and closed after successful submission
