

### Project Setup & Planning Cheat Sheet

| Step | Task | Detailed Instructions & Best Practices |
|------|------|---------------------------------------|
| **1** | **Set up your Git repository** | 1. Create a new folder named `sign-up-form`<br>2. Open terminal in that folder<br>3. Run `git init`<br>4. Create `.gitignore` (add `node_modules/`, `.DS_Store`, etc.)<br>5. Make first commit after basic files are ready<br>**Tip**: Use the same structure as your previous Odin projects (e.g. landing page). |
| **2** | **Set up HTML and CSS files** | 1. Create `index.html` in the root<br>2. Create a `css/` folder<br>3. Inside `css/` create `style.css`<br>4. Link CSS in `<head>`:<br>`<link rel="stylesheet" href="css/style.css">`<br>5. Add basic dummy content (heading, paragraph, and a simple form) to test the link<br>6. Open `index.html` in browser to verify CSS is loading |
| **3** | **Download the design file** | 1. Download the **full-resolution** design image from the lesson page<br>2. Save it in an `images/` folder or keep it handy for reference<br>3. Study the layout carefully:<br>   - Left side: Large background image with dark overlay + logo + text<br>   - Right side: Form area with heading, inputs, button, and link |

### Recommended Project Folder Structure

| Folder / File              | Purpose |
|----------------------------|--------|
| `index.html`               | Main HTML file |
| `css/style.css`            | All your styles |
| `images/`                  | Background image, Odin logo, etc. |
| `README.md`                | Project description (optional but good practice) |
| `.gitignore`               | Ignore unnecessary files |

### Planning the HTML Structure (High-Level)

| Section                    | Suggested HTML Elements |
|----------------------------|-------------------------|
| **Main Container**         | `<div class="container">` (will use Flexbox or Grid) |
| **Left Sidebar (Image)**   | `<div class="sidebar">` with background image + overlay |
| **Logo Area**              | `<div class="logo">` containing Odin logo + "ODIN" text |
| **Right Side (Form)**      | `<div class="form-side">` |
| **Form**                   | `<form>` with proper labels, inputs, and button |
| **Header Text**            | `<h1>` or `<p>` above the form |
| **Footer / Credit**        | Small text at bottom with image credit |

### Initial Dummy Content Suggestion

Add this to `index.html` initially to test your setup:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Sign Up Form</title>
  <link rel="stylesheet" href="css/style.css">
</head>
<body>
  <div class="container">
    <div class="sidebar">
      <!-- Background image + logo will go here -->
      <h1>Dummy Sidebar</h1>
    </div>
    <div class="form-side">
      <h1>Dummy Form Area</h1>
      <form>
        <button type="button">Test Button</button>
      </form>
    </div>
  </div>
</body>
</html>
```

### Next Steps After Setup

1. Make your first Git commit: `"Initial project setup with dummy HTML and CSS"`
2. Plan the HTML skeleton based on the design
3. Start building the left sidebar (background image + overlay + logo)
4. Then move to the form side
