
### Layout Stage – Step-by-Step Cheat Sheet

| Step | Task | Details & Best Implementation |
|------|------|-------------------------------|
| **1** | Write the HTML structure for the main containers | Create three main containers:<br>• Sidebar (left side with background image)<br>• Header (top section of the form side)<br>• Main content (the actual form area) |
| **2** | Apply CSS Grid to build the basic layout | Use CSS Grid on the parent container to create the two-column layout (sidebar + form area) |

### Recommended HTML Skeleton

```html
<body>
  <div class="container">
    
    <!-- Left Sidebar -->
    <div class="sidebar">
      <div class="sidebar-overlay">
        <div class="logo">
          <!-- Odin logo + "ODIN" text will go here -->
        </div>
      </div>
    </div>

    <!-- Right Side: Form Area -->
    <div class="form-side">
      <div class="header">
        <!-- "Create your account" text or similar -->
      </div>
      
      <div class="main-content">
        <!-- The actual form will go here -->
        <form>
          <!-- Form fields will be added later -->
        </form>
      </div>
    </div>

  </div>
</body>
```

### CSS Grid Setup (Core Properties)

| Property                        | Recommended Value                          | Purpose |
|---------------------------------|--------------------------------------------|---------|
| `display`                       | `grid`                                     | Turns `.container` into a grid |
| `grid-template-columns`         | `1fr 1fr` or `minmax(400px, 500px) 1fr`    | Left sidebar + right form area |
| `min-height`                    | `100vh`                                    | Makes the layout fill the full viewport height |
| `gap`                           | `0` (usually no gap between sidebar and form) | — |

### Simple Grid CSS Starter

```css
.container {
  display: grid;
  grid-template-columns: 1fr 1fr;     /* Sidebar : Form area */
  min-height: 100vh;
}

/* Optional: Better control with named areas */
.container {
  display: grid;
  grid-template-columns: 500px 1fr;
  grid-template-areas: 
    "sidebar form";
  min-height: 100vh;
}

.sidebar {
  grid-area: sidebar;
}

.form-side {
  grid-area: form;
}
```

### Layout Structure Summary

| Container          | Class Name       | Role | Grid Area (if using named areas) |
|--------------------|------------------|------|----------------------------------|
| Main Wrapper       | `.container`     | Grid parent | — |
| Left Sidebar       | `.sidebar`       | Background image + logo | `sidebar` |
| Right Form Side    | `.form-side`     | Contains header + form | `form` |
| Header (inside form-side) | `.header`   | "Create your account" text | — |
| Main Form Area     | `.main-content`  | The actual form | — |

### Key Tips for This Stage

- Use **named grid areas** (`grid-template-areas`) — it makes the code much more readable.
- Make the sidebar slightly wider than half (e.g., `500px` or `minmax(400px, 500px)`) to match the design.
- Set `min-height: 100vh` on the grid container so it fills the screen.
- Don’t add detailed styling yet — focus only on getting the basic two-column layout working.
- Test by resizing the browser to ensure the grid behaves correctly.

### Next Actions After Completing This Stage

1. Commit your work: `"Basic grid layout with sidebar and form containers"`
2. Move on to adding the background image and overlay to the sidebar.
3. Then start building the form itself.
