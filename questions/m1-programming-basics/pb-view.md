# pb-view

Module 1 · Programming Basics · workbook section "View Basics" (PB-VIEW-01 – PB-VIEW-02).
Source: the module's Tech Interview Workbook. Rubrics drafted 2026-10-19; flagged items reviewed by the mentor, full review in progress.
Rubrics are for the agent only: never show them or turn them into a model answer (see AGENTS.md).
Extra care topic: go gradual and concrete.

### PB-VIEW-01
**Question:** Explain the difference between JavaScript object data structure and DOM data structure.

**A good answer covers**
- a JS object is your own data in memory
- the DOM is the browser's tree representation of the page
- DOM nodes are objects too, but changing them changes what is shown
- typical flow: data (JS) → render → DOM

**Common misconceptions**
- "the DOM is the HTML file"

**Interviewer follow-ups**
- "Where did you keep your data in a DOM project: in JS or in the page?"

**Practised in:** HTML Animals, View around us, What a tree, Favorite products

**Verify at:** MDN, "Introduction to the DOM"

### PB-VIEW-02
**Question:** What are the necessary steps to change the content of an HTML element using JavaScript?

**A good answer covers**
- select the element (`querySelector`, `getElementById`)
- change it (`textContent`, `innerHTML`, attributes, class)
- or create a new element and insert it (`createElement`, `append`)
- risk of `innerHTML` with user input

**Common misconceptions**
- `textContent` and `innerHTML` are interchangeable

**Interviewer follow-ups**
- "Why might `innerHTML` with user input be dangerous?"

**Practised in:** View around us, What a tree, Product list, Movie DB site, Smol Twitter, More on favorite products, Neighbouring countries

**Verify at:** MDN, `Document.querySelector()`, `Node.textContent`
