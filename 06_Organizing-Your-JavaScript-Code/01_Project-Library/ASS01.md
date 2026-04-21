

### Project Setup Cheat Sheet

| Step | Task | Instructions & Best Practices |
|------|------|-------------------------------|
| **1** | Create the project folder | Choose a clear name, e.g. `library`, `todo-app`, `book-library`, etc. |
| **2** | Initialize Git repository | Open terminal in the project folder and run:<br>`git init` |
| **3** | Create basic folder structure | Recommended structure:<br>```<br>project-name/<br>├── index.html<br>├── css/<br>│   └── style.css<br>├── js/<br>│   └── script.js<br>├── README.md<br>└── .gitignore<br>``` |
| **4** | Create skeleton files | • `index.html` – main HTML file<br>• `css/style.css` – stylesheet<br>• `js/script.js` – JavaScript file |
| **5** | Link CSS and JS in HTML | In `<head>`:<br>`<link rel="stylesheet" href="css/style.css">`<br><br>Before `</body>`:<br>`<script src="js/script.js"></script>` |
| **6** | Add dummy content | Put some placeholder HTML (heading, paragraph, button, container div) to verify everything is linked correctly |
| **7** | Test the setup | Open `index.html` in browser and confirm:<br>• CSS styles are applied<br>• JavaScript file is loaded (add `console.log("JS is working")` to test) |
| **8** | Make first Git commit | `git add .`<br>`git commit -m "Initial project setup with HTML, CSS, and JS skeleton"` |

### Recommended `.gitignore` Content

```gitignore
# Dependencies
node_modules/

# macOS
.DS_Store

# Logs
*.log

# Editor files
.vscode/
.idea/
```

### Basic Starter Files

**index.html**
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Project Name</title>
  <link rel="stylesheet" href="css/style.css">
</head>
<body>
  <h1>Hello from Odin Project</h1>
  
  <script src="js/script.js"></script>
</body>
</html>
```

**js/script.js**
```js
console.log("JavaScript is successfully linked and working!");
```

### Next Steps After Setup

- Commit regularly with clear messages
- Start building the HTML structure
- Style with CSS
- Add interactivity with JavaScript