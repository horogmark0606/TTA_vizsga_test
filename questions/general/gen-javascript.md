# gen-javascript

General module · JavaScript extras.
**General, not course-reviewed:** extra questions that fill gaps the workbooks leave. Not from the course;
kept from the repo's original question bank. Rubrics are for the agent only (see AGENTS.md).

### GEN-JS-01
**Question:** What is a closure? Give an example where it is useful.

**A good answer covers**
- function remembers variables from where it was created
- counters, private state, callbacks.

**Interviewer follow-ups**
- Classic `var` + `setTimeout` loop problem: why, and how to fix?

**Practised in:** (general; not tied to a course project)

_Difficulty: medium · original id: jf-03_

### GEN-JS-02
**Question:** How do you handle errors in JavaScript? Explain `try/catch/finally`.

**A good answer covers**
- `try` risky code, `catch` handles, `finally` always runs
- throw `Error` objects
- catch doesn't catch async errors unless awaited.

**Interviewer follow-ups**
- When would you throw your own error?

**Practised in:** (general; not tied to a course project)

_Difficulty: easy · original id: je-01_

### GEN-JS-03
**Question:** Name common JavaScript error types and what causes them.

**A good answer covers**
- `TypeError` (undefined property), `ReferenceError` (not defined), `SyntaxError`.

**Interviewer follow-ups**
- What causes "Cannot read properties of undefined"?

**Practised in:** (general; not tied to a course project)

_Difficulty: easy · original id: je-02_

### GEN-JS-04
**Question:** What is a Promise? What states does it have?

**A good answer covers**
- object for a future value
- pending, fulfilled, rejected
- `.then/.catch/.finally`.

**Interviewer follow-ups**
- What does `.then` return?

**Practised in:** (general; not tied to a course project)

_Difficulty: medium · original id: as-02_

### GEN-JS-05
**Question:** How do you run several requests in parallel, and when is that better than sequential awaits?

**A good answer covers**
- `Promise.all([...])`
- independent requests
- fails fast
- `allSettled` alternative.

**Interviewer follow-ups**
- What goes wrong with `await` inside `forEach`?

**Practised in:** (general; not tied to a course project)

_Difficulty: hard · original id: as-05_

### GEN-JS-06
**Question:** What is CORS and why do you see CORS errors?

**A good answer covers**
- browser same-origin policy
- server must allow origin via headers
- fix on server (`cors` middleware), not in the frontend.

**Interviewer follow-ups**
- Does Postman show CORS errors? Why not?

**Practised in:** (general; not tied to a course project)

_Difficulty: medium · original id: hr-04_

### GEN-JS-07
**Question:** How do event listeners work? What is event delegation?

**A good answer covers**
- `addEventListener(type, handler)`
- event object
- bubbling
- one listener on parent using `event.target`
- good for dynamic lists.

**Interviewer follow-ups**
- `target` vs `currentTarget`? `preventDefault` use case?

**Practised in:** (general; not tied to a course project)

_Difficulty: medium · original id: dm-03_

### GEN-JS-08
**Question:** Why does `document.querySelector` sometimes return `null`?

**A good answer covers**
- script runs before element exists
- wrong selector
- element created later
- use `defer` / DOMContentLoaded.

**Interviewer follow-ups**
- Where do you put the `<script>` tag?

**Practised in:** (general; not tied to a course project)

_Difficulty: medium · original id: dm-04_
