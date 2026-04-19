

### 1. How Client-Side Form Validation Works

| Concept                        | Description |
|--------------------------------|-------------|
| **Constraint Validation**      | Browser automatically checks form data against rules defined in HTML attributes before submission. |
| **Validation Trigger**         | Mainly on form submission. Some feedback appears on user interaction (blur, input). |
| **Outcome**                    | If all constraints pass → form submits.<br>If any fail → submission is blocked and error message is shown. |
| **Styling Hooks**              | Valid fields match `:valid`.<br>Invalid fields match `:invalid`. |

### 2. Validation Attributes

| Attribute          | Applies To                  | What It Does                                      | Example |
|--------------------|-----------------------------|---------------------------------------------------|---------|
| `required`         | Most inputs, textarea, select | Field must not be empty                           | `<input required>` |
| `minlength`        | Text-based inputs           | Minimum number of characters                      | `minlength="6"` |
| `maxlength`        | Text-based inputs           | Maximum number of characters                      | `maxlength="100"` |
| `min`              | number, range, date/time    | Minimum value                                     | `min="1"` |
| `max`              | number, range, date/time    | Maximum value                                     | `max="100"` |
| `step`             | number, range, date/time    | Allowed increment/step between values             | `step="5"` |
| `pattern`          | Text inputs (not textarea)  | Regular expression the value must match           | `pattern="[0-9]{5}"` |
| `type`             | `<input>`                   | Built-in format validation (email, url, number…)  | `type="email"` |

### 3. Input Types with Built-in Validation

| Input Type              | Built-in Validation Behavior |
|-------------------------|------------------------------|
| `email`                 | Checks for valid email format (supports `multiple`) |
| `url`                   | Checks for valid URL format |
| `number`                | Must be numeric, respects `min`/`max`/`step` |
| `range`                 | Slider with `min`/`max`/`step` |
| `date`, `time`, `datetime-local`, `month`, `week` | Date/time format + `min`/`max` |
| `tel`                   | No strong built-in validation (use `pattern`) |
| `text`                  | Uses `required`, `minlength`/`maxlength`, `pattern` |

### 4. CSS Pseudo-Classes for Styling Validation State

| Pseudo-Class          | When It Matches                                      | Common Use |
|-----------------------|------------------------------------------------------|----------|
| `:valid`              | Element meets all validation constraints             | Green border on good fields |
| `:invalid`            | Element fails one or more constraints                | Red border on bad fields |
| `:required`           | Element has the `required` attribute                 | Visual indicator (*) |
| `:user-valid`         | Valid after user has interacted with it              | Show success only after input |
| `:user-invalid`       | Invalid after user has interacted with it            | Show errors only after blur/input |
| `:in-range`           | Numeric/date value is within `min`/`max`             | — |
| `:out-of-range`       | Numeric/date value is outside `min`/`max`            | — |

### 5. Form & Control Properties & Methods (Native)

| Property / Method          | Applies To             | Description |
|----------------------------|------------------------|-----------|
| `validity`                 | Form controls          | Object containing validation details (`valid`, `valueMissing`, `typeMismatch`, `patternMismatch`, `tooShort`, etc.) |
| `validationMessage`        | Form controls          | Browser-generated localized error message |
| `willValidate`             | Form controls          | `true` if the element is subject to validation |
| `checkValidity()`          | Form controls & `<form>` | Returns `true` if valid; fires `invalid` event if not |
| `reportValidity()`         | Form controls & `<form>` | Checks validity and shows native error message to user |

### 6. Common Validation Patterns

| Goal                              | HTML Example |
|-----------------------------------|--------------|
| Required field                    | `<input type="text" required>` |
| Exact length (e.g. 6 chars)       | `<input minlength="6" maxlength="6">` |
| Email with confirmation           | `<input type="email" required>` |
| Password minimum length           | `<input type="password" minlength="8" required>` |
| Number between 1 and 100          | `<input type="number" min="1" max="100" step="1">` |
| Pattern matching (e.g. fruit)     | `<input pattern="[Bb]anana\|[Cc]herry" required>` |
| Radio group required              | One radio in group has `required` |

### 7. Important Limitations & Notes

- Client-side validation is **not secure** — always validate on the server.
- Native error messages are browser-controlled and localized (hard to customize without JS).
- You cannot fully style the default error popup with CSS.
- Validation mainly triggers on form submission (some live feedback on blur/input).
- Programmatic value changes (via JavaScript) often bypass validation constraints.
- Not all attributes work on every input type (e.g., `pattern` doesn't work on `<textarea>`).

