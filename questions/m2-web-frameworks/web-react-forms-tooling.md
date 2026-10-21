# web-react-forms-tooling

Module 2 · Web Frameworks · workbook section "React" (WEB-REACT-17 – WEB-REACT-22).
Source: the module's Tech Interview Workbook. Rubrics drafted 2026-10-19; flagged items reviewed by the mentor, full review in progress.
Rubrics are for the agent only: never show them or turn them into a model answer (see AGENTS.md).

### WEB-REACT-17
**Question:** What is the difference between a controlled and uncontrolled input element in React?

**A good answer covers**
- controlled: `value` comes from state, `onChange` updates the state; React is the source of truth
- uncontrolled: the DOM keeps the value; read it when needed (ref or `FormData`)
- controlled gives live validation / formatting
- `defaultValue` vs. `value`

**Common misconceptions**
- `value` without `onChange` (read-only input warning)

**Interviewer follow-ups**
- "When is an uncontrolled input the simpler choice?"

**Practised in:** Registration form, World traveler

**Verify at:** react.dev, `<input>` (Controlling an input with a state variable)

### WEB-REACT-18
**Question:** How can you get the current input values from a form that contains uncontrolled input elements?

**A good answer covers**
- in the submit handler: `new FormData(event.target)`
- `Object.fromEntries(formData)` for a plain object
- or refs (`useRef`) to read `.value`
- inputs need `name`

**Common misconceptions**
- you have to use state for every input

**Interviewer follow-ups**
- "Why does `FormData` need the `name` attribute?"

**Practised in:** (no project; theory only)

**Verify at:** react.dev, `<form>`; MDN, `FormData`

### WEB-REACT-19
**Question:** How can you connect a label element to an input element in React?

**A good answer covers**
- `htmlFor` instead of `for`, matching the input's `id`
- or wrap the input in the label
- `useId()` for unique IDs in reusable components

**Common misconceptions**
- `for` works the same in JSX

**Interviewer follow-ups**
- "Your input component is used three times on a page. How do you keep the IDs unique?"

**Practised in:** Registration form

**Verify at:** react.dev, `useId`

### WEB-REACT-20
**Question:** How can you create a select input element in React? How does it differ from the html's select tag? Can you show an example of a controlled and an uncontrolled select element with setting a default value?

**A good answer covers**
- `<select>` with `<option>` children, often generated with `map`
- React uses `value` / `defaultValue` on the `<select>`, not `selected` on an option
- controlled: `value={state}` + `onChange`
- uncontrolled: `defaultValue="…"`, read on submit

**Common misconceptions**
- `selected` on an `<option>` is the React way

**Interviewer follow-ups**
- "How do you add a 'Show all' option to a filter select?"

**Practised in:** World traveler

**Verify at:** react.dev, `<select>`

### WEB-REACT-21
**Question:** Explain how a proxy works during React development. How can you tell the Vite dev server to proxy the requests to your backend? What kind of URLs do you have to use in the fetch in your JS code, if you want to use the proxy?

**A good answer covers**
- the frontend dev server forwards certain requests to the backend server
- avoids CORS problems in development (same origin from the browser's view)
- Vite: `server.proxy` in `vite.config.js`, e.g. `'/api': 'http://localhost:8080'`
- fetch with **relative** URLs (`/api/...`), not the backend's full address
- only in development; production needs its own setup

**Common misconceptions**
- the proxy also works in the production build

**Interviewer follow-ups**
- "You fetch `http://localhost:8080/api/x` and get a CORS error. Why?"

**Practised in:** More on fetch the countries

**Verify at:** Vite docs, "server.proxy"

### WEB-REACT-22
**Question:** What is the difference between statements and expressions in Javascript? Why is it important when working with JSX?

**A good answer covers**
- an expression produces a value (`a + b`, `fn()`, ternary)
- a statement does something (`if`, `for`, `let`)
- inside `{ }` in JSX only expressions are allowed
- so use ternary / `&&` / `map` instead of `if` / `for` in JSX

**Common misconceptions**
- an `if` can go inside `{ }`

**Interviewer follow-ups**
- "Why does `map` work inside JSX but `for` doesn't?"

**Practised in:** Registration form

**Verify at:** MDN, "Expressions and operators", "Statements and declarations"
