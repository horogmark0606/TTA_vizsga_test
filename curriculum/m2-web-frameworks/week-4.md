# Web Frameworks — React

> Project cards for Week 4 — React. Concept level only: no project descriptions,
> tasks or solutions. Question IDs point to topics in `questions/index.yaml`.
> Status: drafted 2026-10-19; mentor review in progress.

## Week 4 — React

### WEB · Reactions around us (solo, week 4)

**Concepts to understand**
- Creating a React app with Vite and cleaning up the template.
- Components as functions that return JSX.
- Props: passing data into a component.
- Reusing one component several times with different props.
- `useState` for form input and for what the page shows.
- Conditional rendering.
- Rendering lists with `map` and `key`.

**Typical pitfalls**
- Missing `key` on list items.
- Changing a prop inside the child component.

**Explain-your-own-code prompts**
- "What's the difference between the props and the state in your component?"
- "Why does the page change when the state changes? Who re-renders what?"

**Related questions:** WEB-REACT-01, WEB-REACT-03, WEB-REACT-04, WEB-REACT-05, WEB-REACT-06, WEB-REACT-12, WEB-REACT-13, WEB-REACT-16

### WEB · Registration form (solo, week 4)

**Concepts to understand**
- Generating form fields from a configuration array with `map`.
- One state object holding every field's value.
- Updating one property of a state object without losing the others.
- Controlled inputs: the value comes from the state.
- Showing something else after submit (ternary in JSX).

**Typical pitfalls**
- `setState({ email: value })` wipes the other fields.
- Mutating the state object directly, so React doesn't re-render.

**Explain-your-own-code prompts**
- "Show me how you update one field. Why don't the other fields get lost?"
- "Is your input controlled or uncontrolled? How do you know?"

**Related questions:** WEB-REACT-10, WEB-REACT-14, WEB-REACT-16, WEB-REACT-17, WEB-REACT-19, WEB-REACT-22, WEB-LANG-04

### WEB · Fetch the countries (solo, week 4)

**Concepts to understand**
- `useEffect` to fetch data when the component first renders.
- The dependency array and why it matters.
- Keeping fetched data in state.
- Showing a list, then the details of one item, then going back (conditional rendering).
- Sorting without mutating the state array.

**Typical pitfalls**
- Fetching in the component body, which causes an infinite loop of renders.
- `sort()` on the state array (mutation).

**Explain-your-own-code prompts**
- "What happens, in order, from the first render until the countries appear?"
- "What would happen if you removed the dependency array?"
- "How do you sort without changing the original array?"

**Related questions:** WEB-REACT-12, WEB-REACT-15, WEB-REACT-16, WEB-FETCH-02, WEB-FETCH-05

### WEB · More on fetch the countries (solo, week 4)

**Concepts to understand**
- Filtering a list live from a search input.
- Splitting a project into a frontend and a backend folder.
- An Express backend for the React frontend; a POST endpoint that stores favourites.
- A dev-server proxy, so the frontend can call the backend with relative URLs.
- Toggling a button's state based on data from the server.

**Typical pitfalls**
- Hard-coding the backend's full address in the frontend instead of using the proxy.
- The favourites view doesn't refresh after adding one.

**Explain-your-own-code prompts**
- "Your React app calls the backend. Which server receives the request first, and what does it do with it?"
- "How does the + button know whether the country is already a favourite?"

**Related questions:** WEB-REACT-21, WEB-REACT-07, WEB-EXPRESS-01, WEB-EXPRESS-09, WEB-REST-04

### WEB · Gotta fetch() 'Em All (team, week 4)

**Concepts to understand**
- Working with a large public API: lists, details, and links between resources.
- Several requests per user action, and the order they complete in.
- Game state in React: what is shown, whose turn it is, HP values.
- Updating state from the previous state.
- Moving between "screens" with conditional rendering.

**Typical pitfalls**
- Stale state when updating HP several times in a row (should use the updater form).
- Showing an empty screen while data is loading.

**Explain-your-own-code prompts**
- "How does a location turn into a creature on the screen? Which requests run, in what order?"
- "Where is the battle state stored, and who changes it?"

**Related questions:** WEB-FETCH-03, WEB-FETCH-05, WEB-REACT-11, WEB-REACT-12, WEB-REACT-16
