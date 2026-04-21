
### Project Setup Cheat Sheet

| Step | Task | Detailed Instructions & Best Practices |
|------|------|---------------------------------------|
| **1** | Create the project folder | Choose a clear name, e.g. `library`, `dashboard`, `book-library`, or `todo-app` |
| **2** | Initialize Git repository | Open terminal in the project folder and run:<br>`git init` |
| **3** | Create recommended folder structure | ```bash
| **4** | Create the skeleton files | - `index.html` (main file)<br>- `css/style.css` (styles)<br>- `js/script.js` (JavaScript logic) |
| **5** | Link CSS and JavaScript in HTML | In `<head>`:<br>`<link rel="stylesheet" href="css/style.css">`<br><br>Before `</body>`:<br>`<script src="js/script.js"></script>` |
| **6** | Add dummy content for testing | Add a heading, a paragraph, and a button in `index.html` to verify that CSS and JS are properly linked |
| **7** | Test the setup | 1. Open `index.html` in your browser<br>2. Confirm CSS styles are applied<br>3. Open DevTools → Console and check that your JS file is running (`console.log("JS is working!")`) |
| **8** | Create `.gitignore` | Add common ignores:<br>`node_modules/`<br>`.DS_Store`<br>`*.log` |
| **9** | Make the first Git commit | ```bash<br>git add .<br>git commit -m "Initial project setup: HTML, CSS, and JS skeleton"<br>``` |

### Starter Code Templates

**index.html**
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Library App</title>
  <link rel="stylesheet" href="css/style.css">
</head>
<body>
  <h1>My Library</h1>
  <button id="new-book-btn">Add New Book</button>

  <div id="library"></div>

  <script src="js/script.js"></script>
</body>
</html>
```

**js/script.js**
```js
console.log("✅ JavaScript is successfully linked and working!");

document.getElementById('new-book-btn').addEventListener('click', () => {
  console.log("New Book button clicked");
});
```

### Quick Checklist After Setup

- [ ] Git repository initialized
- [ ] Proper folder structure created
- [ ] HTML, CSS, and JS files linked correctly
- [ ] Dummy content visible in browser
- [ ] JavaScript console message appears
- [ ] First commit made with clear message

Would you like me to customize this cheat sheet for a specific project?  
For example:
- Library App
- Dashboard
- Restaurant Page
- Todo App

