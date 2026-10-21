# Web Frameworks — project cards

> Module 2 of the FullStack course: `fetch` and async JavaScript, responsive
> CSS, Node file handling, Express, REST, React, testing, Firebase.
> Question IDs (`WEB-…`) refer to `WEB-questions.md`.
>
> Status: **draft, mentor review pending.**

---

## Week 1 — Fetch

### WEB · Fetch the sky (solo, week 1)

**Concepts to understand**
- Reading API documentation to find the right endpoint and parameters.
- Building a URL with query parameters (API key, date).
- `fetch` returns a Promise; the body is read with a second async step (`.json()`).
- `async` / `await` vs. `.then()`: what waits for what.
- Rendering fetched data into the DOM, including different media types.
- Re-fetching when user input changes (date picker), and keeping buttons in sync with it.
- Disabling a control when its action makes no sense.

**Typical pitfalls**
- Using the data before the Promise has resolved (`undefined` or a pending Promise).
- Forgetting `await` on `.json()`.
- Date arithmetic and formatting mistakes when moving one day back or forward.

**Explain-your-own-code prompts**
- "Walk me through your fetch function line by line. At which points does the code wait, and what for?"
- "What would you see if you removed one `await`? Why?"
- "How does the date input stay in sync when someone clicks Previous?"

**Related questions:** WEB-FETCH-01, WEB-FETCH-02, WEB-FETCH-03, WEB-FETCH-04, WEB-FETCH-05, WEB-FETCH-07

### WEB · Fetch the Globe (solo, week 1)

**Concepts to understand**
- Two kinds of endpoint: a list endpoint and a "one item by code" endpoint.
- Rendering a list from fetched data and reacting to clicks on its items.
- Navigating a list with previous / next, with buttons disabled at the ends.
- Reading and writing the URL query string, so a state can be linked to and reloaded.
- Following references in the data (neighbours by code) with further requests.

**Typical pitfalls**
- Fetching the full list again on every click.
- Not handling an invalid or missing code in the URL.
- Updating the page but not the URL (or the other way round).

**Explain-your-own-code prompts**
- "When the page loads with a code in the URL, what happens first, second, third?"
- "Why does the URL change when you click Next? What does that give the user?"

**Related questions:** WEB-FETCH-01, WEB-FETCH-05, WEB-FETCH-06, WEB-FETCH-07, WEB-LANG-11

### WEB · My social media (solo, week 1)

**Concepts to understand**
- Flexbox: container vs. items, main axis vs. cross axis.
- Building a full page layout (navbar, side column, main area, footer) from nested flex containers.
- Proportional widths, `gap`, alignment.
- Placing items on opposite sides (e.g. incoming vs. own messages).

**Typical pitfalls**
- Putting flex properties on the item when they belong on the container (or vice versa).
- Fixed pixel widths that break on smaller screens.

**Explain-your-own-code prompts**
- "Which elements are flex containers in your layout? Why those?"
- "How did you push your own messages to the other side?"

**Related questions:** WEB-RESP-01, WEB-RESP-04, WEB-RESP-06, WEB-RESP-07, WEB-RESP-08

### WEB · My Little Gallery (solo, week 1)

**Concepts to understand**
- Using a CSS framework (Bootstrap) instead of writing all CSS by hand.
- The grid system: rows, columns, breakpoint classes.
- Changing the number of items per row by screen size.
- A responsive navbar.
- Filtering and "favourites" views rendered from the same data.

**Typical pitfalls**
- Mixing custom CSS and framework classes until they fight.
- Rendering the filtered view by hiding elements instead of re-rendering from data.

**Explain-your-own-code prompts**
- "Which classes decide how many images are in a row? What happens at each breakpoint?"
- "When the user searches, where does the filtered list come from?"

**Related questions:** WEB-RESP-01, WEB-RESP-03, WEB-RESP-04, WEB-RESP-05, WEB-LANG-09, WEB-LANG-11

### WEB · Weather in the Capitals (team, week 1)

**Concepts to understand**
- Reading documentation for **several** APIs and combining their data.
- Requests that depend on the result of an earlier request (chained async calls).
- Several independent requests: one after the other vs. in parallel (`Promise.all`).
- Sorting and rendering a list from fetched data.
- Previous / next navigation and disabled states.
- Responsive design for mobile and desktop.

**Typical pitfalls**
- Making requests in a loop without understanding the order they finish in.
- No loading or error state when one of the APIs fails.
- Too many requests (no reuse of data you already have).

**Explain-your-own-code prompts**
- "Which request has to finish before which other one can start? Show me where your code waits."
- "One of the APIs is down. What does your user see?"
- "How did your team split the work between the APIs?"

**Related questions:** WEB-FETCH-03, WEB-FETCH-04, WEB-FETCH-06, WEB-RESP-01, WEB-RESP-05, WEB-LANG-10

---

## Week 2 — Files and Express

### WEB · File handling (solo, week 2)

**Concepts to understand**
- Reading and writing files with Node's `fs` (synchronous versions).
- Checking that a file exists before using it.
- Relative paths, and building paths that work on every OS (`path.join`, the script's own folder).
- Text encoding (`utf-8`) and line breaks (`\n`).
- Overwriting vs. appending.
- File system flags (read-only, append).

**Typical pitfalls**
- Paths that only work when the script is started from one particular folder.
- Overwriting a file when you meant to append.
- Counting lines wrong because of a trailing newline.

**Explain-your-own-code prompts**
- "Start your script from a different folder. Does it still find the file? Why?"
- "What's the difference between how you created the file and how you added to it?"

**Related questions:** WEB-LANG-03, WEB-LANG-07

### WEB · Your very own TODO list (solo, week 2)

**Concepts to understand**
- Promise-based (async) file reading and writing.
- Command-line arguments (`process.argv`).
- JSON: serialising data to a file and parsing it back.
- CRUD on a data structure: create, read, update, delete.
- Generating a new ID from existing data.
- Meaningful error messages when an item isn't found.

**Typical pitfalls**
- Writing the file before the read has finished.
- Forgetting to write the changes back after modifying the data.
- Generating an ID that can collide after a delete.

**Explain-your-own-code prompts**
- "Walk me through the 'create' command: what is read, what changes, what is written, in what order?"
- "Where would it break if you removed an `await`?"
- "How do you generate a new ID? Delete the last todo and create a new one. What happens?"

**Related questions:** WEB-FETCH-04, WEB-LANG-05, WEB-LANG-07, WEB-LANG-12, WEB-REST-03

### WEB · Rookie Homecook (solo, week 2)

**Concepts to understand**
- An Express server: creating the app, defining a route, starting to listen on a port.
- Sending HTML, files and JSON from a route.
- Serving static files from a folder.
- Frontend `fetch` to your **own** server (GET, then POST).
- The JSON body-parsing middleware and why the server needs it.
- Submitting a form with JavaScript instead of the browser default.

**Typical pitfalls**
- POST body is `undefined` because the JSON middleware is missing.
- Forgetting the `Content-Type` header when sending JSON from the frontend.
- The page reloads on submit (default behaviour not prevented).

**Explain-your-own-code prompts**
- "A user submits the form. Trace the data: from the input, through the request, into the server, and back to the page."
- "What does the JSON middleware actually do to the request?"
- "Which URL is a page and which one is an API endpoint in your server? How can you tell?"

**Related questions:** WEB-EXPRESS-01, WEB-EXPRESS-03, WEB-EXPRESS-04, WEB-EXPRESS-05, WEB-EXPRESS-06, WEB-EXPRESS-07, WEB-EXPRESS-09, WEB-REST-09, WEB-REST-10, WEB-REST-13, WEB-LANG-08

### WEB · Movie Data Server (solo, week 2)

**Concepts to understand**
- Designing API endpoints that return JSON.
- A route that takes a dynamic value (route parameter) and finds the matching item.
- Responding to "not found".
- A client page that fetches from the API and renders lists and details.
- Keeping the browser URL in sync with what is shown.

**Typical pitfalls**
- Special characters in titles that break the URL (encoding).
- Always answering 200, even when nothing was found.

**Explain-your-own-code prompts**
- "How does your server know which movie was requested? Show me where that value comes from."
- "What does your endpoint send back for a title that doesn't exist?"

**Related questions:** WEB-EXPRESS-02, WEB-EXPRESS-08, WEB-EXPRESS-09, WEB-EXPRESS-10, WEB-EXPRESS-12, WEB-FETCH-07, WEB-REST-01

---

## Week 3 — REST

### WEB · Use (solo, week 3)

**Concepts to understand**
- A REST API for one resource: a route per operation, each with the right HTTP method.
- PUT (replace everything) vs. PATCH (change only the fields that were sent).
- POST creates and generates a unique ID; DELETE answers with a "no content" status.
- Using a JSON file as a simple database: read → change → write.
- An editor page with forms for create and edit; the edit form is pre-filled.

**Typical pitfalls**
- A PUT implementation that behaves like PATCH (or the other way round).
- Wrong status codes (200 for everything).
- Lost updates because the file is read and written at the wrong time.

**Explain-your-own-code prompts**
- "Send a PUT with only one field. What happens to the other fields? Now the same with PATCH."
- "Why does DELETE answer the way it does?"
- "How does the edit form know the current values?"

**Related questions:** WEB-REST-01, WEB-REST-03, WEB-REST-05, WEB-REST-06, WEB-REST-08, WEB-REST-11, WEB-EXPRESS-12

### WEB · Movie editor (solo, week 3)

**Concepts to understand**
- The same REST pattern applied to a different, richer resource.
- Mapping form fields to object properties, including numbers and lists.
- Refreshing the list after each change.
- Validating input on the client and on the server.

**Typical pitfalls**
- Numbers saved as strings because form values are always strings.
- The list on the page doesn't update after a change.

**Explain-your-own-code prompts**
- "What type is the year when it reaches your server? Where do you convert it?"
- "After a successful edit, how does the page get the fresh data?"

**Related questions:** WEB-REST-03, WEB-REST-05, WEB-REST-09, WEB-REST-12, WEB-REST-16

### WEB · Favorite data editor (solo, week 3)

**Concepts to understand**
- Designing your own data structure: keys, types, IDs.
- Designing the API endpoints for it yourself.
- An editor on a separate route.
- Putting the ID of the edited object into the URL, so it can be reloaded and linked.

**Typical pitfalls**
- A data structure that makes some operations awkward later.
- Endpoints named after actions instead of resources.

**Explain-your-own-code prompts**
- "Why did you design the data this way? What would you change now?"
- "Read your endpoint list aloud. Is it clear which resource each one works on?"

**Related questions:** WEB-REST-07, WEB-REST-08, WEB-FETCH-01, WEB-EXPRESS-12

### WEB · Yet Another Online Shop (team, week 3)

**Concepts to understand**
- One Express server serving both the website (static files) and the API.
- Two clients for the same API: a public shop and an editor site.
- A cart and checkout flow (client-side state, then an order request).
- Error handling on both sides: status codes from the server, messages in the UI.
- Responsive layout.

**Typical pitfalls**
- Business rules only in the frontend (the server accepts anything).
- No feedback to the user when a request fails.

**Explain-your-own-code prompts**
- "A customer places an order. Walk me through every request and response."
- "What happens if someone sends an invalid order straight to the API, without your frontend?"
- "How did your team agree on the API before building both sides?"

**Related questions:** WEB-EXPRESS-01, WEB-EXPRESS-06, WEB-REST-01, WEB-REST-02, WEB-REST-03, WEB-REST-04, WEB-RESP-01

---

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

---

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

---

## Week 6 — Authentication

### WEB · Set up Authentication with Firebase (solo, week 6)

**Concepts to understand**
- Registering a web app and initialising Firebase in a React project.
- The Auth SDK: getting the auth instance.
- Enabling the email / password provider.
- Sign-up and sign-in calls, and showing success and error messages.
- Listening to auth state changes to know who is signed in.

**Typical pitfalls**
- Config values committed to the repo without understanding which ones are secret.
- Showing raw error codes to the user.

**Explain-your-own-code prompts**
- "How does your app find out that the user is signed in? Who tells it?"
- "What happens, step by step, when sign-up fails?"

**Related questions:** WEB-AUTH-01, WEB-AUTH-02, WEB-AUTH-05, WEB-AUTH-07

### WEB · My Secrets (solo, week 6)

**Concepts to understand**
- Working in an existing React app: reading its navigation before changing it.
- Sign up, sign in and sign out with the Auth SDK.
- Storing the current user in app state, and persisting the login across reloads.
- Changing the view based on auth state; protecting a page.
- Form validation: matching passwords, live password-strength feedback.

**Typical pitfalls**
- The "protected" page is only hidden in the menu, not really protected.
- A flash of the wrong page while auth state is still loading.

**Explain-your-own-code prompts**
- "A signed-out user opens the secret page directly. What exactly stops them?"
- "Reload the page while signed in. How does your app know who you are?"

**Related questions:** WEB-AUTH-02, WEB-AUTH-03, WEB-AUTH-04, WEB-REACT-16, WEB-REST-09

### WEB · Employee Madness Firebase (solo, week 6)

**Concepts to understand**
- Getting an existing full-stack app running: environment variables, database rules, seed data.
- Several sign-in providers (Google and email / password).
- Rules that allow access only to authenticated users.
- Filtering, searching, sorting and pagination of a list.
- A new entity and a relation between entities (who uses which equipment).
- A route with a dynamic segment.
- React Context for shared app state.

**Typical pitfalls**
- Pagination and filters that don't work together.
- Environment variables missing or committed.

**Explain-your-own-code prompts**
- "Where does the app read its configuration from? Why not hard-code it?"
- "How did you connect equipment to employees in the data?"
- "Filter, then go to page 2. What should happen, and what does your code do?"

**Related questions:** WEB-AUTH-06, WEB-AUTH-07, WEB-APP-01, WEB-APP-05, WEB-FBDB-05

### WEB · Freestyle Firebase Project, Part 2 (team, week 6)

**Concepts to understand**
- Replanning: adding features to an existing product.
- Sign up and sign in; protected pages with redirect to login.
- Security rules that protect data at the database level, not just in the UI.
- Building and deploying the app.

**Typical pitfalls**
- Protection only in the UI: the data is still open in the database.
- The deployed app behaves differently from the local one (config, routes).

**Explain-your-own-code prompts**
- "Someone skips your UI and calls the database directly. What stops them?"
- "What happens during the build, and what actually gets deployed?"

**Related questions:** WEB-AUTH-04, WEB-AUTH-06, WEB-APP-02, WEB-APP-03, WEB-APP-04

---

## Weeks 7–8 — Personal assessment practice

### WEB · Personal Assessment Base Project and Practice (solo, week 7)

**Concepts to understand**
- Getting an unfamiliar project running: dev server, local emulators, seeded data.
- Working on a separate branch.
- Reading existing code before changing it.
- Implementing small features in someone else's codebase under time pressure.

**Typical pitfalls**
- Starting to code before understanding the data flow.
- Large changes that are hard to explain afterwards.

**Explain-your-own-code prompts**
- "Before you changed anything: how did data get from the database to the screen?"
- "Explain your smallest change and why it was enough."

**Related questions:** WEB-APP-03, WEB-REACT-03, WEB-FBDB-03
