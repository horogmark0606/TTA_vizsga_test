# Web Frameworks — Testing, Context, Firebase

> Project cards for Week 5 — Testing, Context, Firebase. Concept level only: no project descriptions,
> tasks or solutions. Question IDs point to topics in `questions/index.yaml`.
> Status: drafted 2026-10-19; mentor review in progress.

## Week 5 — Testing, Context, Firebase

### WEB · Testing basics (solo, week 5)

**Concepts to understand**
- Running an existing test suite and reading the results.
- Code coverage: what it measures and what it doesn't.
- Refactoring safely: change the code, and the tests stay green.
- Writing tests for edge cases (empty input) and normal cases.
- Writing code against existing tests.

**Typical pitfalls**
- Thinking 100% coverage means "no bugs".
- Only testing the happy path.

**Explain-your-own-code prompts**
- "Which of your tests would catch a bug that the others miss?"
- "What does the coverage report tell you, and what can't it tell you?"

**Related questions:** WEB-TEST-01, WEB-TEST-02, WEB-TEST-03, WEB-TEST-05

### WEB · We test (solo, week 5)

**Concepts to understand**
- Setting up a Node project for testing (`package.json`, dev dependency, `.gitignore`).
- One test per behaviour: naming tests by the case they check.
- Arrange / act / assert.
- Testing that a function throws for invalid input.
- Splitting a function into helpers and testing them separately.
- HTML coverage reports.

**Typical pitfalls**
- Several unrelated assertions in one test.
- `toBe` on objects or arrays.

**Explain-your-own-code prompts**
- "Read me the names of your tests. Do they describe the cases clearly?"
- "How do you test that an error is thrown?"

**Related questions:** WEB-TEST-01, WEB-TEST-03, WEB-TEST-04, WEB-TEST-08

### WEB · Context Cascade (solo, week 5)

**Concepts to understand**
- Prop drilling: passing a value through components that don't use it.
- React Context: creating it, providing a value, reading it with `useContext`.
- Putting state *and* its setter into a context.
- When Context is the right tool, and when plain props are better.

**Typical pitfalls**
- Using a component that reads the context outside its Provider.
- Putting everything into Context "just in case".

**Explain-your-own-code prompts**
- "Before your change, which components passed the colour without using it?"
- "Where is the Provider? What happens to a component rendered outside it?"

**Related questions:** WEB-APP-05, WEB-REACT-05, WEB-REACT-11

### WEB · Firebase Real Time Database Quickstart (solo, week 5)

**Concepts to understand**
- Creating a Firebase project and a Realtime Database; the Firebase CLI config files.
- Security rules: what they control, and why "open to everyone" is only for development.
- Using the database through its REST API with `fetch`.
- A component structure: list, item, form; child-to-parent communication with callback props.
- Updating local state after a request succeeds.

**Typical pitfalls**
- Leaving open rules in a real app.
- Updating the UI before the request succeeded (or never syncing it after).

**Explain-your-own-code prompts**
- "The user saves a todo. Which component does what, and when is the request sent?"
- "How does the child tell the parent that something was saved?"
- "What do your current security rules allow? Who could read or write your data?"

**Related questions:** WEB-FBDB-01, WEB-FBDB-02, WEB-FBDB-03, WEB-FBDB-04, WEB-REACT-07

### WEB · World traveler (solo, week 5)

**Concepts to understand**
- CRUD against the Realtime Database REST API.
- Select, checkbox and radio inputs in React.
- Several filters at once, and how they combine.
- Derived values (a total calculated from the list) instead of storing them separately.
- Inline edit: switching an item into a form and back.
- Accessible labels.

**Typical pitfalls**
- Storing derived values in state, so they get out of sync.
- A checkbox's `checked` not tied to the data.

**Explain-your-own-code prompts**
- "Where do you calculate the total weight? Why there?"
- "How do the two filters combine? Show me with an example."

**Related questions:** WEB-FBDB-03, WEB-REACT-17, WEB-REACT-20, WEB-REST-12, WEB-REST-14, WEB-LANG-11, WEB-LANG-12

### WEB · Freestyle Firebase Project, Part 1 (team, week 5)

**Concepts to understand**
- Planning a product: entities, their properties and types.
- Full CRUD with Firebase and React.
- Loading and error states shown to the user.
- Filtering and sorting.
- Responsive design with a CSS framework.
- Managing state across many components.

**Typical pitfalls**
- Too big a scope for the time available.
- Loading and error states added at the end, or never.

**Explain-your-own-code prompts**
- "Show me your entity design. Why these properties and types?"
- "What does the user see while data is loading, and when it fails?"
- "Which decision would you make differently if you started again?"

**Related questions:** WEB-FBDB-02, WEB-FBDB-05, WEB-REACT-03, WEB-REACT-16, WEB-RESP-04
