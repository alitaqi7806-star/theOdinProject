

### Do’s for Form Validation UX

| Do ✅                                      | Why It Improves UX |
|-------------------------------------------|--------------------|
| Show validation errors **inline** and close to the relevant field | Users can immediately see and fix the problem without scanning the whole form |
| Provide **clear, helpful, and actionable** error messages | Tell users exactly what’s wrong and how to fix it (e.g., “Email must be in format name@example.com”) |
| Use **positive language** where possible and focus on the solution | Reduces frustration (e.g., “Please enter a valid email” instead of “Invalid email”) |
| Validate on **blur** (when user leaves the field) or after typing with a short delay | Gives real-time feedback without being annoying during typing |
| Show **success states** (green tick or border) for correctly filled fields | Builds confidence and visual progress |
| Use the **holy trinity** of feedback: color + icon + text message | Makes errors accessible and scannable for all users |
| Keep the **Submit button enabled** at all times | Allows users to see all errors at once on submission |
| Highlight **required fields** clearly (asterisk + text) | Prevents confusion about what’s mandatory |
| Group related fields with `<fieldset>` + `<legend>` | Improves accessibility and logical flow |
| Provide helpful **placeholder text** and examples where needed | Guides users without replacing labels |

### Don’ts for Form Validation UX

| Don’t ❌                                   | Why It Hurts UX |
|-------------------------------------------|-----------------|
| Show **real-time validation** while the user is still typing | It’s distracting, annoying, and can cause premature error flashes |
| Use **witty or sarcastic** error messages | Users want to complete the task, not be entertained |
| **Disable the Submit button** until the form is fully valid | Users can’t see all errors at once and feel blocked |
| Hide or bury error messages at the top/bottom of the form | Users have to hunt for what’s wrong |
| Rely only on **color** for errors (no text or icon) | Not accessible for color-blind users or screen readers |
| Use vague messages like “Invalid input” | Leaves users confused about how to fix it |
| Force users to use **calendar pickers** for dates like year of birth | Typing is often faster and less frustrating for long ranges |
| Remove default **focus indicators** | Hurts keyboard and accessibility users |
| Over-validate simple fields (e.g., strict phone format without country selector) | Creates unnecessary friction |
| Show errors only on form submission without any live feedback | Feels like a surprise and increases cognitive load |

### Bonus UX Tips from Discussions

- **Timing matters**: Best practice is often **blur + submit** validation.
- **Server-side validation** is still required — client-side is only for better UX.
- **Progressive disclosure**: Show only relevant errors at the right time.
- For complex forms: Consider **multi-step wizards** with per-step validation.
