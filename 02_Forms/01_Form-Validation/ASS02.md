

### 1. Core Form Structure

| Element / Attribute       | Purpose                                              | Recommended Usage |
|---------------------------|------------------------------------------------------|-------------------|
| **`<form>`**              | Container for all form controls                      | Always include `action` and `method` |
| **`action`**              | URL where form data is sent                          | Full URL or relative path |
| **`method`**              | HTTP method (`get` or `post`)                        | Use `post` for most forms (login, contact, signup) |
| **`novalidate`**          | Disables browser validation                          | Useful during development or when using custom JS validation |
| **`autocomplete`**        | Allows browser autofill                              | `"on"` (default) or `"off"` |

### 2. Labels & Accessibility

| Best Practice                  | Correct Code Example |
|--------------------------------|----------------------|
| **Explicit Label**             | `<label for="email">Email Address</label>`<br>`<input type="email" id="email" name="email">` |
| **Fieldset Grouping**          | `<fieldset>`<br>`<legend>Personal Details</legend>`<br>`... controls ...`</fieldset>` |
| **Why it matters**             | Improves click area, screen reader support, and semantic structure |

### 3. Validation Attributes (Constraint Validation)

| Attribute          | Description                                          | Example |
|--------------------|------------------------------------------------------|---------|
| `required`         | Field must be filled                                 | `<input type="text" required>` |
| `minlength`        | Minimum character length                             | `minlength="8"` |
| `maxlength`        | Maximum character length                             | `maxlength="100"` |
| `min`              | Minimum numeric or date value                        | `min="1"` or `min="2025-01-01"` |
| `max`              | Maximum numeric or date value                        | `max="100"` |
| `step`             | Allowed increment for number/range/date              | `step="5"` |
| `pattern`          | Regular expression the value must match              | `pattern="[A-Za-z]{3,}"` |
| `type`             | Built-in format validation (email, url, number, etc.)| `type="email"` |

### 4. HTML5 Input Types with Built-in Validation

| Input Type                  | Validation Behavior                                  | Common Attributes |
|-----------------------------|------------------------------------------------------|-------------------|
| `email`                     | Checks valid email format                            | `multiple`, `required` |
| `url`                       | Checks valid URL format                              | `required` |
| `number`                    | Numeric only + min/max/step                          | `min`, `max`, `step` |
| `range`                     | Slider with min/max/step                             | `min`, `max`, `step` |
| `tel`                       | No strong validation (use `pattern`)                 | `pattern` |
| `date` / `time` / `datetime-local` | Date/time picker with min/max                    | `min`, `max` |
| `color`                     | Color picker                                         | — |
| `file`                      | File upload (use with `accept`)                      | `accept`, `multiple` |

### 5. CSS Pseudo-Classes for Validation Feedback

| Pseudo-Class       | When It Applies                                      | Typical Use |
|--------------------|------------------------------------------------------|-------------|
| `:valid`           | Field passes all constraints                         | Green border |
| `:invalid`         | Field fails one or more constraints                  | Red border |
| `:required`        | Field has the `required` attribute                   | Show asterisk |
| `:optional`        | Field does not have `required`                       | — |
| `:user-valid`      | Valid after user interaction                         | Show success state |
| `:user-invalid`    | Invalid after user interaction                       | Show error state |

### 6. Best Practices & Tips from the Guide

| Area                       | Recommendation |
|----------------------------|--------------|
| **Accessibility**          | Always use proper `<label>` with `for` attribute. Group with `<fieldset>` + `<legend>`. |
| **User Experience**        | Provide helpful placeholder text and clear error messages. |
| **Security**               | Client-side validation is for convenience only — always validate on the server. |
| **Styling**                | Use `:valid` and `:invalid` for visual feedback. Avoid removing default focus styles. |
| **Performance**            | Keep forms short and logical. Group related fields. |
| **Novalidate**             | Useful when you want full control with custom JavaScript validation. |
| **Title Attribute**        | Can provide custom tooltip for `pattern` validation errors. |

### 7. Quick Complete Example

```html
<form action="/submit" method="post">
  <fieldset>
    <legend>Contact Information</legend>
    
    <label for="name">Full Name <span aria-hidden="true">*</span></label>
    <input type="text" id="name" name="full_name" required minlength="2">
    
    <label for="email">Email Address <span aria-hidden="true">*</span></label>
    <input type="email" id="email" name="email" required>
    
    <label for="message">Message</label>
    <textarea id="message" name="message" rows="5"></textarea>
  </fieldset>
  
  <button type="submit">Send</button>
</form>
```
