# Web Frameworks — Fetch

> Project cards for Week 1 — Fetch. Concept level only: no project descriptions,
> tasks or solutions. Question IDs point to topics in `questions/index.yaml`.
> Status: drafted 2026-10-19; mentor review in progress.

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
