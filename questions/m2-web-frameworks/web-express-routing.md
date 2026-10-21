# web-express-routing

Module 2 · Web Frameworks · workbook section "Express" (WEB-EXPRESS-07 – WEB-EXPRESS-12).
Source: the module's Tech Interview Workbook. Rubrics drafted 2026-10-19; flagged items reviewed by the mentor, full review in progress.
Rubrics are for the agent only: never show them or turn them into a model answer (see AGENTS.md).
Extra care topic: go gradual and concrete.

### WEB-EXPRESS-07
**Question:** What does the built-in JSON middleware (`express.json()`) do?

**A good answer covers**
- parses request bodies with `Content-Type: application/json`
- puts the result on `req.body`
- without it `req.body` is `undefined`
- the client must send the right content type

**Common misconceptions**
- it formats the *response* as JSON

**Interviewer follow-ups**
- "The body is `undefined` even though you added the middleware. What do you check?"

**Practised in:** Rookie Homecook

**Verify at:** Express docs, API reference, `express.json()`

### WEB-EXPRESS-08
**Question:** How does Express.js handle HTTP request/response cycles? Explain the process of receiving and responding to requests using Express.js middlewares and route handlers.

**A good answer covers**
- a request arrives and goes through middleware and routes in registration order
- each one either responds or passes on with `next()`
- the first matching route handler sends the response
- the cycle ends when the response is sent; nothing answered → request hangs
- error-handling middleware `(err, req, res, next)`

**Common misconceptions**
- several handlers can each send a response

**Interviewer follow-ups**
- "What happens if no route matches?"

**Practised in:** Movie Data Server

**Verify at:** Express docs, "Writing middleware"

### WEB-EXPRESS-09
**Question:** How does routing work in Express.js? Explain how to define routes and handle different HTTP methods (GET, POST, etc.) in an Express.js application.

**A good answer covers**
- `app.get`, `app.post`, `app.put`, `app.patch`, `app.delete` with a path and a handler
- the same path can have different handlers per method
- route parameters and query strings
- `express.Router` to group routes

**Common misconceptions**
- one route handles all methods by default

**Interviewer follow-ups**
- "How would you split your routes into several files?"

**Practised in:** Rookie Homecook, Movie Data Server, More on fetch the countries

**Verify at:** Express docs, "Routing"

### WEB-EXPRESS-10
**Question:** What are the various methods available in Express.js for sending responses to clients? Explain the differences between res.send() and res.json() in Express.js.

**A good answer covers**
- `res.send`, `res.json`, `res.sendFile`, `res.status`, `res.sendStatus`, `res.redirect`, `res.end`
- `res.json` always sends JSON with the JSON content type
- `res.send` decides the type from the argument (string → HTML, object → JSON)
- `res.status(…)` sets the code and is chained

**Common misconceptions**
- `res.status(404)` alone sends a response

**Interviewer follow-ups**
- "How do you send a 404 with a JSON error message?"

**Practised in:** Movie Data Server

**Verify at:** Express docs, API reference, "res"

### WEB-EXPRESS-11
**Question:** What is the purpose of the next() function in Express.js middleware? How can you use it to pass control to the next middleware function in the chain or to terminate the middleware processing?

**A good answer covers**
- `next()` passes control to the next matching middleware / route
- not calling it, and not responding, leaves the request hanging
- sending a response (instead of `next()`) ends the chain
- `next(err)` jumps to error-handling middleware

**Common misconceptions**
- `next()` sends the response

**Interviewer follow-ups**
- "An auth middleware: what does it do for a logged-in user, and what for a logged-out one?"

**Practised in:** (no project; theory only)

**Verify at:** Express docs, "Writing middleware"

### WEB-EXPRESS-12
**Question:** Explain the concept of route parameters in Express.js. How can you extract dynamic values from the URL path using route parameters, and how are these values accessed within route handlers?

**A good answer covers**
- named segments in the path: `/items/:id`
- read in the handler from `req.params.id`
- the value is always a string (convert if needed)
- vs. query strings (`req.query`)

**Common misconceptions**
- `req.params.id` is a number

**Interviewer follow-ups**
- "When would you use a route parameter, and when a query string?"

**Practised in:** Movie Data Server, Use, Favorite data editor

**Verify at:** Express docs, "Routing" (Route parameters)
