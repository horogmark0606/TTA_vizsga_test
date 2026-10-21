# web-html-forms

Module 2 · Web Frameworks · workbook section "REST and CRUD" (WEB-REST-09 – WEB-REST-16).
Source: the module's Tech Interview Workbook. Rubrics drafted 2026-10-19; flagged items reviewed by the mentor, full review in progress.
Rubrics are for the agent only: never show them or turn them into a model answer (see AGENTS.md).

### WEB-REST-09
**Question:** How do you handle form submissions using JavaScript? Explain the process of capturing form data and preventing the default form submission behavior.

**A good answer covers**
- listen to the form's `submit` event (not the button's click)
- `event.preventDefault()` stops the page reload
- read values (inputs, or `new FormData(form)`)
- send them with `fetch`, then update the UI

**Common misconceptions**
- listening to the button click is the same

**Interviewer follow-ups**
- "Why `submit` on the form rather than `click` on the button?"

**Practised in:** Rookie Homecook, Movie editor, My Secrets

**Verify at:** MDN, "HTMLFormElement: submit event", `FormData`

### WEB-REST-10
**Question:** Explain the required elements necessary to define a form in HTML.

**A good answer covers**
- `<form>` (with `action` / `method` when not handled by JS)
- input elements with `name`
- labels
- a submit button

**Common misconceptions**
- inputs without `name` are submitted

**Interviewer follow-ups**
- "What does a `<button>` inside a form do by default?"

**Practised in:** Rookie Homecook

**Verify at:** MDN, "Your first form"

### WEB-REST-11
**Question:** What is the purpose of the required attribute in HTML form elements? How does it enforce mandatory input fields and prevent form submission without the required information?

**A good answer covers**
- marks a field as mandatory
- the browser blocks submit and shows a message
- part of built-in constraint validation
- client-side only: the server must still validate

**Common misconceptions**
- `required` is enough validation

**Interviewer follow-ups**
- "Why do you still need validation on the server?"

**Practised in:** Use

**Verify at:** MDN, "Client-side form validation"

### WEB-REST-12
**Question:** Explain the different types of form input fields available in HTML. How do input types like text, number, email, checkbox, and radio buttons differ, and how are they used in forms?

**A good answer covers**
- text, number, email (built-in validation, mobile keyboards)
- checkbox: independent on / off (`checked`)
- radio: one choice in a group (same `name`)
- others: password, date, select, textarea
- values arrive as strings

**Common misconceptions**
- a number input gives you a number value

**Interviewer follow-ups**
- "How do you group radio buttons so only one can be selected?"

**Practised in:** Movie editor, World traveler

**Verify at:** MDN, `<input>` types

### WEB-REST-13
**Question:** Can you explain the purpose of the name attribute in the context of form submission?

**A good answer covers**
- the key under which the value is sent
- only named fields are submitted
- groups radio buttons
- used by `FormData`

**Common misconceptions**
- `id` and `name` do the same thing

**Interviewer follow-ups**
- "What's the difference between `id` and `name` on an input?"

**Practised in:** Rookie Homecook

**Verify at:** MDN, `<input>` (name attribute)

### WEB-REST-14
**Question:** Can you explain how we can connect a label tag to a form element?

**A good answer covers**
- `<label for="id">` matching the input's `id`
- or wrap the input inside the label
- clicking the label focuses the input
- accessibility: screen readers read the label

**Common misconceptions**
- placeholder replaces a label

**Interviewer follow-ups**
- "Why is a placeholder not a replacement for a label?"

**Practised in:** World traveler

**Verify at:** MDN, `<label>`

### WEB-REST-15
**Question:** How can you dynamically manipulate or modify form elements using JavaScript? Explain how to add or remove form fields dynamically based on user interaction or specific conditions.

**A good answer covers**
- create inputs with `createElement`, set attributes, append them
- remove with `remove()`
- change properties: `disabled`, `value`, `required`
- react to events (change, input) to decide what to show

**Common misconceptions**
- (none typical)

**Interviewer follow-ups**
- "How would you show an extra field only when a checkbox is ticked?"

**Practised in:** (no project; theory only)

**Verify at:** MDN, "Introduction to the DOM"

### WEB-REST-16
**Question:** How can you convert form data into a format that can be easily transmitted or processed by the server?

**A good answer covers**
- `new FormData(form)`
- `Object.fromEntries(formData)` gives a plain object
- `JSON.stringify` + `Content-Type: application/json`
- or URL-encoded / multipart (for files)
- convert types where needed (numbers, booleans)

**Common misconceptions**
- `FormData` can be passed to `JSON.stringify` directly

**Interviewer follow-ups**
- "How do you send a file to the server?"

**Practised in:** Movie editor

**Verify at:** MDN, `FormData`, `Object.fromEntries()`
