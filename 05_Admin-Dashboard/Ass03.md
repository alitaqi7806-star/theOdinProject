
### Nesting in CSS Grid – Dashboard Project Cheat Sheet

| Step | Task | Recommended Approach & Tips |
|------|------|-----------------------------|
| **1** | Nest child elements under parent containers | Build the layout hierarchically. Use multiple nested grids instead of trying to do everything with one giant grid. |
| **2** | Sidebar: Navigation + Branding | Create a nested grid inside `.sidebar` to separate the logo/branding area from the navigation links. |
| **3** | Header: Search bar, user info, and buttons | Use a nested grid (or Flexbox) inside the header to align search input, user avatar, name, and action buttons. |
| **4** | Main Content: Projects, Announcements, Trending | Divide the main area into three sections using another grid (or sub-grids). |
| **5** | Add dummy content & placeholder images | Fill every section with realistic dummy text and images so you can properly test positioning and spacing. |

### Recommended Nested Grid Structure

| Parent Container       | Child Elements (Nested Grid / Flex) | Purpose |
|------------------------|-------------------------------------|---------|
| **.dashboard** (Main Grid) | `.sidebar`, `.header`, `.main-content` | Overall page layout (usually 2 or 3 columns) |
| **.sidebar**           | `.branding`, `.nav`                 | Logo area + navigation links |
| **.header**            | `.search`, `.user-info`, `.actions` | Search bar + user profile + buttons |
| **.main-content**      | `.projects`, `.announcements`, `.trending` | Three main content sections |

### Best Practices for Nesting

| Area                  | Technique Recommendation                          | Why It Works Well |
|-----------------------|---------------------------------------------------|-------------------|
| **Sidebar**           | Nested Grid (2 rows) or Flexbox                   | Clean separation between branding and navigation |
| **Header**            | Flexbox (most common) or nested Grid              | Excellent for horizontal alignment and spacing |
| **Main Content**      | CSS Grid with `grid-template-areas` or `grid-template-columns` | Allows easy control over the three-column layout (Projects | Announcements | Trending) |
| **Cards / Items**     | Flexbox inside each card                          | Great for internal card layout (title, description, icons) |

### Example Nested Structure (High-Level)

```html
<div class="dashboard">                    <!-- Main Grid -->
  
  <aside class="sidebar">                  <!-- Nested Grid -->
    <div class="branding">…</div>
    <nav class="nav">…</nav>
  </aside>

  <header class="header">                  <!-- Flexbox or Nested Grid -->
    <div class="search">…</div>
    <div class="user-info">…</div>
    <div class="actions">…</div>
  </header>

  <main class="main-content">              <!-- Nested Grid -->
    <section class="projects">…</section>
    <section class="announcements">…</section>
    <section class="trending">…</section>
  </main>

</div>
```

### Key Tips for This Stage

- Don’t try to solve the entire layout with one single grid — **nesting** makes the code much cleaner and more maintainable.
- Use `grid-template-areas` on the main dashboard grid for readability.
- Inside `.main-content`, you can use another grid with 2 or 3 columns (e.g., projects take more space).
- Add plenty of **dummy content** early:
  - Project cards with titles, descriptions, and fake images
  - Announcement text
  - Trending items with avatars and names
- Use placeholder images from `https://picsum.photos/` or Unsplash during development.
- Keep testing in the browser frequently as you nest elements.

### Common Nesting Patterns Used in This Project

| Section           | Most Common Technique          | Reason |
|-------------------|--------------------------------|--------|
| Sidebar           | Nested Grid (rows)             | Easy vertical stacking |
| Header            | Flexbox                        | Best for horizontal distribution |
| Main Content      | CSS Grid                       | Controls multiple content sections |
| Individual Cards  | Flexbox                        | Internal alignment of content |
