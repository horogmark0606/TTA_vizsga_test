# web-react-components

Module 2 · Web Frameworks · workbook section "React" (WEB-REACT-01 – WEB-REACT-10).
Source: the module's Tech Interview Workbook. Rubrics drafted 2026-10-19; flagged items reviewed by the mentor, full review in progress.
Rubrics are for the agent only: never show them or turn them into a model answer (see AGENTS.md).

### WEB-REACT-01
**Question:** What is React.js and what are its key features?

**A good answer covers**
- a JavaScript library for building user interfaces
- components
- declarative: describe the UI for a given state; React updates the DOM
- JSX, one-way data flow, hooks
- large ecosystem

**Common misconceptions**
- "React is a full framework with routing and data fetching built in"

**Interviewer follow-ups**
- "What does 'declarative' mean compared with your Programming Basics DOM code?"

**Practised in:** Reactions around us

**Verify at:** react.dev, "Learn"

### WEB-REACT-02
**Question:** Explain the concept of virtual DOM and how it contributes to React's performance.

> Note for the agent: Changed since the workbook was written: React's current docs (react.dev) no longer use the term "virtual DOM". They describe a **render** phase (React calculates what changed) and a **commit** phase (React applies the minimal DOM changes). Accept a virtual-DOM answer. Then mention that the docs now explain it as render and commit, and suggest reading "Render and Commit" on react.dev.

**A good answer covers**
- an in-memory description of the UI (React elements)
- on change React builds a new tree and compares it with the old one
- only the differences are applied to the real DOM
- the real DOM is the slow part, so fewer changes is faster
- (current docs' wording: render = calculate, commit = apply only the differences)

**Common misconceptions**
- "the virtual DOM makes every app faster than plain JS"

**Interviewer follow-ups**
- "What is actually slow about touching the real DOM?"

**Practised in:** (no project; theory only)

**Verify at:** react.dev, "Render and Commit"

### WEB-REACT-03
**Question:** Explain the component-based architecture in React.js. How do components work, and how can they be composed to build complex user interfaces?

**A good answer covers**
- a component is a function that returns JSX
- small, reusable pieces with a single job
- composed into a tree: parents render children, pass props
- `children` prop for wrapping
- names start with a capital letter

**Common misconceptions**
- one big component is simpler

**Interviewer follow-ups**
- "How did you decide where to split components in your project?"

**Practised in:** Reactions around us, Freestyle Firebase Project, Part 1, Personal Assessment Base Project and Practice

**Verify at:** react.dev, "Your First Component"

### WEB-REACT-04
**Question:** What is the significance of JSX in React.js? Explain how JSX combines HTML-like syntax with JavaScript code and how it is transpiled into regular JavaScript during the build process.

> Note for the agent: Changed since the workbook was written: the tool that compiles JSX in Vite has changed over versions (esbuild before, Oxc in current Vite; Babel in older setups). Accept any of these if the idea is right: JSX becomes plain JavaScript function calls at build time. Mention that the tooling changes often and suggest checking the Vite docs ("Features" → JSX) for the version they use.

**A good answer covers**
- HTML-like syntax inside JavaScript
- `{ }` embeds JavaScript expressions
- differences from HTML: `className`, `htmlFor`, camelCase attributes, one root element
- compiled by the build tool into function calls that create React elements (Babel historically; earlier Vite versions used esbuild, current Vite uses Oxc)

**Common misconceptions**
- the browser understands JSX directly

**Interviewer follow-ups**
- "Why can't you write an `if` statement inside `{ }` in JSX?"

**Practised in:** Reactions around us

**Verify at:** react.dev, "Writing Markup with JSX"

### WEB-REACT-05
**Question:** What are props in React and how are they used to pass data between components? Explain the concept of props and how they facilitate parent-child component communication.

**A good answer covers**
- inputs to a component, passed like attributes
- data flows down, from parent to child
- read-only for the child
- any value: strings, numbers, objects, functions, JSX

**Common misconceptions**
- a child can change its props

**Interviewer follow-ups**
- "How can a child tell the parent something happened?"

**Practised in:** Reactions around us, Context Cascade

**Verify at:** react.dev, "Passing Props to a Component"

### WEB-REACT-06
**Question:** How can you access and utilize props within a functional component in React? Explain how to extract and use props using the destructuring syntax.

**A good answer covers**
- the component receives one `props` object
- `function Card({ title, price })` destructures it in the parameter
- default values in the destructuring
- `...rest` for the remaining props

**Common misconceptions**
- props arrive as separate arguments

**Interviewer follow-ups**
- "What do you get if the parent didn't pass `price`?"

**Practised in:** Reactions around us

**Verify at:** react.dev, "Passing Props to a Component"

### WEB-REACT-07
**Question:** How can you pass callback functions as props in React? Provide an example of how to pass a function from a parent component to a child component, enabling the child to communicate with the parent.

**A good answer covers**
- the parent defines a function (often one that updates its state) and passes it as a prop
- the child calls it, e.g. in an event handler, with data as arguments
- the parent's state changes, so it re-renders
- naming: `onSomething` prop, `handleSomething` function

**Common misconceptions**
- passing `onSave={save()}` instead of `onSave={save}`

**Interviewer follow-ups**
- "Show me one place in your project where a child talks to its parent."

**Practised in:** More on fetch the countries, Firebase Real Time Database Quickstart

**Verify at:** react.dev, "Responding to Events"

### WEB-REACT-08
**Question:** Explain the concept of spreading props in React. How can the spread operator be used to pass multiple props from a parent component to a child component in a concise manner?

**A good answer covers**
- `<Child {...obj} />` passes each property as a prop
- useful for forwarding props to a wrapped element
- order matters: later props override earlier ones
- downside: unclear which props a component really gets

**Common misconceptions**
- spread passes the object as a single prop

**Interviewer follow-ups**
- "`<Input {...props} type="text" />`: which `type` wins?"

**Practised in:** (no project; theory only)

**Verify at:** react.dev, "Passing Props to a Component" (Forwarding props)

### WEB-REACT-09
**Question:** Explain the concept of default props (with ES6 JS syntax) in React. How can you define default values for props in a component to handle cases where the prop value is not explicitly passed?

**A good answer covers**
- default values in parameter destructuring: `function Btn({ size = 'md' })`
- used when the prop is missing or `undefined`
- not used for `null`
- `defaultProps` is legacy: removed for function components in React 19

**Common misconceptions**
- an empty string triggers the default

**Interviewer follow-ups**
- "The parent passes `size={null}`. What does the child get?"

**Practised in:** (no project; theory only)

**Verify at:** react.dev, "Passing Props to a Component" (default value)

### WEB-REACT-10
**Question:** Explain the immutability principle when working with props and states in React. Why is it important to avoid directly modifying prop values within a component, and what are some best practices for maintaining immutability?

**A good answer covers**
- props are owned by the parent; state is changed only through the setter
- React spots changes by **reference**: a mutated object looks unchanged, so no re-render
- create new arrays / objects: spread, `map`, `filter`
- mutation causes bugs that are hard to trace

**Common misconceptions**
- `state.push(x); setState(state)` works

**Interviewer follow-ups**
- "Why doesn't the screen update after you push into the state array?"

**Practised in:** Registration form

**Verify at:** react.dev, "Updating Objects in State", "Updating Arrays in State"
