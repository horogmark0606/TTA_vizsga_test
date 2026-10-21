# Web Frameworks — Files and Express

> Project cards for Week 2 — Files and Express. Concept level only: no project descriptions,
> tasks or solutions. Question IDs point to topics in `questions/index.yaml`.
> Status: drafted 2026-10-19; mentor review in progress.

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
