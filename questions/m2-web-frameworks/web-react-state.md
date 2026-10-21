# web-react-state

Module 2 · Web Frameworks · workbook section "React" (WEB-REACT-11 – WEB-REACT-16).
Source: the module's Tech Interview Workbook. Rubrics drafted 2026-10-19; flagged items reviewed by the mentor, full review in progress.
Rubrics are for the agent only: never show them or turn them into a model answer (see AGENTS.md).

### WEB-REACT-11
**Question:** How does React.js handle state management? Explain the concept of state and how it differs from props.

**A good answer covers**
- state: data a component owns and that changes over time
- changing state with the setter re-renders the component
- props come from outside and are read-only; state is internal
- lifting state up to share it between components
- Context for deep sharing

**Common misconceptions**
- every value should be in state (derived values shouldn't)

**Interviewer follow-ups**
- "Two sibling components need the same data. Where does the state go?"

**Practised in:** Gotta fetch() 'Em All, Context Cascade

**Verify at:** react.dev, "State: A Component's Memory", "Sharing State Between Components"

### WEB-REACT-12
**Question:** What are React hooks? Explain the purpose and benefits of hooks like useState, and useEffect in React.js.

**A good answer covers**
- functions that give function components React features (`use…`)
- `useState`: a value that survives re-renders, plus a setter that triggers a re-render
- `useEffect`: side effects (fetching, subscriptions) after render; the dependency array controls when it re-runs; cleanup function
- rules: call only at the top level, only in components or custom hooks

**Common misconceptions**
- `useEffect` without a dependency array runs only once

**Interviewer follow-ups**
- "What's the difference between `[]`, `[id]` and no array at all?"

**Practised in:** Reactions around us, Fetch the countries, Gotta fetch() 'Em All

**Verify at:** react.dev, `useState`, `useEffect`

### WEB-REACT-13
**Question:** Explain the concept of virtual DOM reconciliation in React.js. How does React efficiently update and render components by performing minimal DOM manipulations?

> Note for the agent: Same terminology change as WEB-REACT-02. Accept "virtual DOM" wording, mention the render / commit framing of the current docs, and point to react.dev ("Render and Commit", "Preserving and Resetting State").

**A good answer covers**
- after a state change, React re-renders and compares the new element tree with the previous one
- same type at the same position → update; different type → replace the subtree
- `key`s identify list items between renders
- only the changes are committed to the DOM

**Common misconceptions**
- `key` only removes a console warning

**Interviewer follow-ups**
- "What can go wrong when you use the array index as `key`?"

**Practised in:** Reactions around us

**Verify at:** react.dev, "Preserving and Resetting State", "Rendering Lists"

### WEB-REACT-14
**Question:** Explain how to manage complex state objects with useState. Explain techniques like object spreading or merging to update specific properties within an object state.

**A good answer covers**
- the setter **replaces** the state; it doesn't merge
- `setForm({ ...form, email: value })`
- nested objects need spreading at each level
- updater form `setForm(prev => …)` when the new state depends on the old
- computed keys `[name]: value` for generic input handlers

**Common misconceptions**
- `useState` merges like old class `setState`

**Interviewer follow-ups**
- "Write one change handler that works for every input in a form."

**Practised in:** Registration form

**Verify at:** react.dev, "Updating Objects in State"

### WEB-REACT-15
**Question:** Why is it important to provide a new array as an argument to the state setter function when adding an item to an existing array?

**A good answer covers**
- React compares the old and new state by reference
- `push` keeps the same array, so React sees "no change"
- `[...items, newItem]` creates a new array → re-render
- it also keeps the old state intact (no hidden side effects)

**Common misconceptions**
- `push` then `setItems(items)` works

**Interviewer follow-ups**
- "How do you remove an item? How do you update one?"

**Practised in:** Fetch the countries

**Verify at:** react.dev, "Updating Arrays in State"

### WEB-REACT-16
**Question:** How does conditional rendering work in React? Explain the different techniques and approaches available to conditionally render components or content based on certain conditions or state values. How can it be used to control the visibility or behavior of components based on user interactions or other dynamic conditions?

**A good answer covers**
- `if` / early `return` before the JSX
- ternary `cond ? <A/> : <B/>` inside JSX
- `cond && <A/>` (and the `0` trap)
- returning `null` to render nothing
- driven by state, so user actions change what is shown

**Common misconceptions**
- `{n && <List/>}` is safe when `n` is `0`

**Interviewer follow-ups**
- "What does `{items.length && <List />}` show for an empty list?"

**Practised in:** Reactions around us, Registration form, Fetch the countries, Gotta fetch() 'Em All, Freestyle Firebase Project, Part 1, My Secrets

**Verify at:** react.dev, "Conditional Rendering"
