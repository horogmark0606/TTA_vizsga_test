# web-fetch

Module 2 · Web Frameworks · workbook section "Fetch" (WEB-FETCH-01 – WEB-FETCH-07).
Source: the module's Tech Interview Workbook. Rubrics drafted 2026-10-19; flagged items reviewed by the mentor, full review in progress.
Rubrics are for the agent only: never show them or turn them into a model answer (see AGENTS.md).
Extra care topic: go gradual and concrete.

### WEB-FETCH-01
**Question:** How does a query string parameter in a URL contribute to web application functionality? Explain how query string parameters are typically used to pass data between web pages or APIs.

**A good answer covers**
- `?key=value&key2=value2` after the path
- used for filters, search, pagination, API keys, page state
- makes a state shareable / bookmarkable
- reading them: `URLSearchParams` (client), `req.query` (Express)
- values must be URL-encoded

**Common misconceptions**
- query strings are secure for secrets

**Interviewer follow-ups**
- "Why is a search term usually in the query string and not in the path?"

**Practised in:** Fetch the sky, Fetch the Globe, Favorite data editor

**Verify at:** MDN, `URLSearchParams`

### WEB-FETCH-02
**Question:** What is the purpose and functionality of the fetch function in JavaScript?

**A good answer covers**
- makes HTTP requests from JavaScript
- returns a Promise that resolves to a `Response`
- the body is read separately (`.json()`, `.text()`), which is also async
- method, headers, body can be set in an options object

**Common misconceptions**
- `fetch` returns the data directly

**Interviewer follow-ups**
- "Why are there two `await`s in a typical fetch?"

**Practised in:** Fetch the sky, Fetch the countries

**Verify at:** MDN, "Using the Fetch API"

### WEB-FETCH-03
**Question:** Explain the syntax of the fetch function and how it handles asynchronous operations. Compare and contrast the syntax of making HTTP requests using fetch with async/await versus the syntax using .then() and .catch(). What are the key differences and benefits of using the async/await syntax in terms of code structure and readability?

**A good answer covers**
- `fetch(url, options)` returns a Promise
- `.then()` chains callbacks; `.catch()` handles errors
- `async` / `await` pauses inside an async function until the Promise settles; errors via `try` / `catch`
- same mechanism underneath; async/await reads top-to-bottom
- `await` only works inside an `async` function (or at module top level)
- an `async` function always returns a Promise

**Common misconceptions**
- `await` blocks the whole program
- async/await is a different mechanism from Promises

**Interviewer follow-ups**
- "What does an `async` function return if you `return 5` from it?"
- "Rewrite a two-step `.then()` chain with `await`."

**Practised in:** Fetch the sky, Weather in the Capitals, Gotta fetch() 'Em All

**Verify at:** MDN, "async function", "Using promises"

### WEB-FETCH-04
**Question:** What is asynchronicity in JavaScript? Name some typical use cases when asynchronicity is needed.

**A good answer covers**
- start a slow operation, continue with other work, handle the result later
- JavaScript is single-threaded; the event loop runs callbacks when results are ready
- use cases: network requests, timers, file I/O, user events, database calls
- the UI stays responsive

**Common misconceptions**
- "async code runs in parallel threads"

**Interviewer follow-ups**
- "In what order are these logged: a `console.log`, a `setTimeout(…, 0)`, another `console.log`?"

**Practised in:** Fetch the sky, Weather in the Capitals, Your very own TODO list

**Verify at:** MDN, "Introducing asynchronous JavaScript"

### WEB-FETCH-05
**Question:** How can you handle the response received from a fetch request?

**A good answer covers**
- check `response.ok` / `response.status`
- read the body with the right method (`.json()`, `.text()`, `.blob()`)
- then use the data (render, store in state)
- the body can only be read once

**Common misconceptions**
- `response` itself is the data

**Interviewer follow-ups**
- "What happens if you call `.json()` on a response whose body isn't JSON?"

**Practised in:** Fetch the sky, Fetch the Globe, Fetch the countries, Gotta fetch() 'Em All

**Verify at:** MDN, `Response`

### WEB-FETCH-06
**Question:** How does the fetch function handle errors and handle HTTP status codes? Provide an example of using fetch to handle different types of responses, including successful and error responses.

**A good answer covers**
- the Promise rejects only on network failure (no response)
- 4xx / 5xx still **resolve**, so check `response.ok` yourself
- throw or branch on `!response.ok`; `try` / `catch` around the await
- show a useful message to the user

**Common misconceptions**
- "a 404 goes into `.catch()`"

**Interviewer follow-ups**
- "The server returns 500. Does your `catch` run? Why or why not?"

**Practised in:** Fetch the Globe, Weather in the Capitals

**Verify at:** MDN, "Using the Fetch API" (Checking response status)

### WEB-FETCH-07
**Question:** Explain the parts of a URL.

**A good answer covers**
- protocol / scheme, host (domain), port
- path
- query string
- fragment (`#…`)

**Common misconceptions**
- the fragment is sent to the server

**Interviewer follow-ups**
- "Which part changes when you go from your dev server to production?"

**Practised in:** Fetch the sky, Fetch the Globe, Movie Data Server

**Verify at:** MDN, "What is a URL?"
