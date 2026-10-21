# web-express-basics

Module 2 · Web Frameworks · workbook section "Express" (WEB-EXPRESS-01 – WEB-EXPRESS-06).
Source: the module's Tech Interview Workbook. Rubrics drafted 2026-10-19; flagged items reviewed by the mentor, full review in progress.
Rubrics are for the agent only: never show them or turn them into a model answer (see AGENTS.md).
Extra care topic: go gradual and concrete.

### WEB-EXPRESS-01
**Question:** Explain the concept of client-server communication in the context of web development. How does information flow between the client and the server in a typical client-server architecture?

**A good answer covers**
- the client (browser, app) sends a request; the server processes it and sends a response
- over HTTP(S); the client always starts
- the server holds shared data / logic; the client presents it
- a concrete flow from their project

**Common misconceptions**
- the server can push to a plain HTTP client at any time

**Interviewer follow-ups**
- "Your React app shows a list. Trace it from the click to the database and back."

**Practised in:** Rookie Homecook, Yet Another Online Shop, More on fetch the countries

**Verify at:** MDN, "Client-Server overview"

### WEB-EXPRESS-02
**Question:** What is the role of HTTP requests and responses in web development? Explain the structure of an HTTP request and an HTTP response.

**A good answer covers**
- request: method, URL / path, headers, optional body
- response: status code (and text), headers, optional body
- stateless: each request stands alone
- headers carry metadata (content type, auth, caching)

**Common misconceptions**
- GET requests have a body

**Interviewer follow-ups**
- "Where in DevTools can you see a request's headers and body?"

**Practised in:** Movie Data Server

**Verify at:** MDN, "HTTP messages"

### WEB-EXPRESS-03
**Question:** What is Express.js and how does it simplify web application development in Node.js? Explain the core features and benefits of using Express.js as a web framework.

**A good answer covers**
- a minimal web framework for Node.js
- routing by method and path
- middleware pipeline
- helpers for requests and responses (`req.params`, `res.json`, static files)
- compared with Node's raw `http` module

**Common misconceptions**
- "Express is a frontend framework"

**Interviewer follow-ups**
- "What would you have to write yourself without Express?"

**Practised in:** Rookie Homecook

**Verify at:** Express docs, "Hello world" / "Guide"

### WEB-EXPRESS-04
**Question:** What are middlewares in Express.js? Can you list some examples of the built-in middleware?

**A good answer covers**
- functions `(req, res, next)` that run in order for matching requests
- can read / change `req` / `res`, end the response, or call `next()`
- built-in: `express.json()`, `express.urlencoded()`, `express.static()`
- third-party examples (e.g. `cors`) and own ones (logging, auth)

**Common misconceptions**
- middleware only runs before routes

**Interviewer follow-ups**
- "How would you write a middleware that logs every request?"

**Practised in:** Rookie Homecook

**Verify at:** Express docs, "Using middleware"

### WEB-EXPRESS-05
**Question:** How can you tell Express.js to use a middleware?

**A good answer covers**
- `app.use(middleware)` for every request
- `app.use('/path', middleware)` for a path prefix
- as an extra argument on one route: `app.get('/x', mw, handler)`
- order of registration matters

**Common misconceptions**
- order doesn't matter

**Interviewer follow-ups**
- "You register the JSON middleware after your routes. What happens?"

**Practised in:** Rookie Homecook

**Verify at:** Express docs, "Using middleware"

### WEB-EXPRESS-06
**Question:** Explain the process of handling static files (e.g., CSS, images) in Express.js. How can you configure Express.js to serve static assets from a specific directory in your application?

**A good answer covers**
- `app.use(express.static('folder'))`
- files are served by their path relative to that folder
- optional mount path: `app.use('/static', express.static(...))`
- use an absolute path (`path.join(__dirname, …)`) so it works from any start folder

**Common misconceptions**
- the folder name appears in the URL by default

**Interviewer follow-ups**
- "Your CSS works locally but not when started from another folder. Why?"

**Practised in:** Rookie Homecook, Yet Another Online Shop

**Verify at:** Express docs, "Serving static files in Express"
