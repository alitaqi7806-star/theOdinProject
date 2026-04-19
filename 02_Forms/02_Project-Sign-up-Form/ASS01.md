

### Project Overview
Build a beautiful, responsive **sign-up form** that closely matches the provided design. Focus on clean HTML structure, good form semantics, accessibility, and styling with CSS (including Flexbox/Grid and custom properties).

### Step-by-Step Setup Instructions

| Step | Task | Detailed Instructions & Tips |
|------|------|------------------------------|
| **1** | **Set up your Git repository** | 1. Create a new folder for the project (e.g., `sign-up-form`)<br>2. Open the folder in your terminal<br>3. Run `git init`<br>4. Create a `.gitignore` file (ignore node_modules, etc. if needed)<br>5. Make your first commit after setting up files<br>**Tip**: Refer to your previous Odin projects (like the landing page) for the exact workflow. |
| **2** | **Set up your HTML and CSS files** | 1. Create `index.html`<br>2. Create a `css/` folder and add `style.css` inside it<br>3. Link the CSS file in the `<head>` of HTML: `<link rel="stylesheet" href="css/style.css">`<br>4. Add some **dummy content** (e.g., a heading, a simple form with a few inputs, and a button) to test the link<br>5. Open the file in your browser to confirm everything works |
| **3** | **Download the design file** | 1. Go to the lesson page and download the **full-resolution design image** (there are usually two versions: overall layout + details)<br>2. Study the layout carefully:<br>   - Left side: Large background image with overlay text/logo<br>   - Right side: The actual sign-up form<br>3. Note key elements: header with logo, form fields, “Already have an account?” link, footer/credit area<br>4. Decide on your HTML structure (main container, sidebar/image section, form section) |

### Additional Setup Tips from the Lesson

| Item | Details |
|------|---------|
| **Background Image** | The left panel uses a large background image. Download a high-quality photo from Unsplash (or similar). Credit the author in your footer. |
| **Fonts** | The design uses specific fonts (usually one for headings and one for body). You can use system fonts or Google Fonts. |
| **Colors** | Pay attention to the exact green accent color used for the “Create Account” button and other highlights. |
| **Layout Approach** | Most students use **Flexbox** (or CSS Grid) for the two-column layout. The form itself works well with a combination of Flexbox + good spacing. |
| **First Commit** | After completing steps 1–3 and verifying the dummy content displays correctly, make an initial commit with a message like “Project setup + dummy HTML/CSS”. |

### Recommended Project Folder Structure

```
sign-up-form/
├── index.html
├── css/
│   └── style.css
├── images/          (for background image and any other assets)
├── README.md
└── .gitignore
```

### Quick Next Steps After Setup
- Plan your HTML skeleton (header, main with two sections: image + form)
- Start with mobile-first or desktop-first layout
- Use semantic HTML (`<form>`, `<fieldset>`, proper `<label>`s, etc.)
