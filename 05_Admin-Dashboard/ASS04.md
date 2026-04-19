

### Gather Assets – Dashboard Project Cheat Sheet

| Step | Task | Details & Recommendations |
|------|------|---------------------------|
| **1** | Decide on your design approach | You have two options:<br>• **Option A**: Closely recreate the example dashboard shown in the lesson<br>• **Option B**: Create your own original dashboard design<br>**Recommendation**: If you're still building confidence with Grid, start by recreating the example first. |
| **2** | Gather Icons | • Source: **Material Design Icons** (official Google library)<br>• Format: **SVG** (preferred for scalability and styling)<br>• Download only the icons you need (e.g., home, search, notifications, settings, etc.)<br>• Save them in an `images/icons/` folder |
| **3** | Choose and include Fonts | • Default suggestion: **Roboto** (same as the example)<br>• How to include: Use **Google Fonts**<br>• Add this in the `<head>` of your HTML:<br>`<link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;500;700&display=swap" rel="stylesheet">`<br>• Then apply in CSS: `font-family: 'Roboto', sans-serif;` |
| **4** | Prepare Placeholder Images | • Use **picsum.photos** for quick random images during development<br>• Example: `https://picsum.photos/id/1015/300/200`<br>• Later replace with real project-related images if desired |
| **5** | Organize Assets Folder | Recommended structure:<br>```<br>dashboard/<br>├── index.html<br>├── css/<br>│   └── style.css<br>├── images/<br>│   ├── icons/          ← All SVG icons<br>│   └── placeholders/   ← Dummy images<br>└── README.md<br>``` |

### Font Setup (Roboto Example)

```html
<!-- In <head> -->
<link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;500;700&display=swap" rel="stylesheet">
```

```css
/* In style.css */
body {
  font-family: 'Roboto', system-ui, sans-serif;
}

h1, h2, h3 {
  font-weight: 500;        /* Medium weight for headings */
}

p, span {
  font-weight: 400;        /* Regular weight for body text */
}
```

### Icon Strategy Tips

| Icon Type              | Recommendation |
|------------------------|----------------|
| Navigation icons       | Home, Dashboard, Projects, Messages, Settings |
| Action icons           | Notifications, Search, Add, More |
| User-related           | Profile, Avatar, Logout |
| Format                 | Always use **SVG** for crisp scaling and easy color control with CSS |

### Quick Asset Checklist

- [ ] Grid layout is complete and working
- [ ] Material Design Icons SVGs downloaded and saved
- [ ] Google Fonts (Roboto) linked correctly
- [ ] Dummy/placeholder images ready
- [ ] Folder structure organized (`images/icons/`)
- [ ] Basic dummy content added to test layout

### Pro Tips

- Start with **SVG icons** — they are lightweight and you can change their color easily with CSS (`fill` or `currentColor`).
- Use **Roboto** for a clean, modern look that matches most professional dashboards.
- Keep your `images/` folder well organized from the beginning.
