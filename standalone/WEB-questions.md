# Web Frameworks — interview question rubrics

> Questions come from the module's Tech Interview Workbook (students already
> have them). Rubrics are for the agent only: compare silently, never show
> them, never turn them into a model answer. See the agent instructions.
> Which projects practise each question: `WEB-index.md`.
>
> Status: **draft, mentor review pending.**

---

## JavaScript Language Features

### WEB-LANG-01
**Question:** What is ECMAScript? What is the difference between Javascript & ECMAScript?

**A good answer covers**
- ECMAScript: the language specification (standard), maintained by TC39 / Ecma
- JavaScript: an implementation of that spec, plus host APIs (DOM in browsers, `fs` in Node)
- versions (ES6 / ES2015 and yearly releases since)

**Common misconceptions**
- "ECMAScript is a different language"

**Interviewer follow-ups**
- "Is `document.querySelector` part of ECMAScript?"

**Verify at:** MDN, "JavaScript technologies overview"

### WEB-LANG-02
**Question:** Explain the concept of "block scoping" introduced in ES6. How does it differ from function scoping?

**A good answer covers**
- `let` / `const` live only inside the nearest `{ }` block
- `var` is function-scoped and ignores blocks
- classic example: a loop variable used by callbacks
- temporal dead zone

**Common misconceptions**
- "`var` inside an `if` is local to the `if`"

**Interviewer follow-ups**
- "Why do callbacks in a `for (var i…)` loop all see the same `i`?"

**Verify at:** MDN, `let`, "Block statement"

### WEB-LANG-03
**Question:** What are template literals in ES6 and how do they improve string manipulation in JavaScript?

**A good answer covers**
- backtick strings with `${expression}` interpolation
- multi-line strings without `\n`
- more readable than `+` concatenation
- any expression inside `${}` (not only variables)

**Common misconceptions**
- only variables can go inside `${}`

**Interviewer follow-ups**
- "How would you build an HTML snippet with a template literal, and what's the risk?"

**Verify at:** MDN, "Template literals"

### WEB-LANG-04
**Question:** What is the "spread operator" in ES6 and how can it be used to manipulate arrays and objects more effectively?

**A good answer covers**
- `...` expands an iterable / object into elements / properties
- copying and merging arrays and objects
- adding items without mutating: `[...arr, item]`, `{ ...obj, key: value }`
- it makes a **shallow** copy
- function call arguments: `Math.max(...nums)`

**Common misconceptions**
- spread makes a deep copy

**Interviewer follow-ups**
- "You spread an object that contains an array, then push to that array. What happens to the original?"

**Verify at:** MDN, "Spread syntax"

### WEB-LANG-05
**Question:** Explain the concept of "destructuring assignment" in ES6. How does it simplify variable assignment and object/array manipulation?

**A good answer covers**
- object destructuring by property name; array destructuring by position
- default values and renaming
- rest element (`...rest`)
- common uses: function parameters (React props), swapping variables, `useState`

**Common misconceptions**
- array destructuring matches by name

**Interviewer follow-ups**
- "What does `const [a, b] = useState(0)` destructure, and why an array?"

**Verify at:** MDN, "Destructuring assignment"

### WEB-LANG-06
**Question:** How does ES6 introduce the concept of "default function parameters"? Provide an example of using default parameters in a function.

**A good answer covers**
- `function f(x = 10) {}`
- the default is used when the argument is `undefined` (missing)
- `null` does **not** trigger the default
- defaults can use earlier parameters

**Common misconceptions**
- any falsy value triggers the default

**Interviewer follow-ups**
- "What does `f(null)` give with `x = 10`?"

**Verify at:** MDN, "Default parameters"

### WEB-LANG-07
**Question:** Explain the concept of "modules" introduced in ES6. How do they improve code organization and reusability in JavaScript?

**A good answer covers**
- each file has its own scope; nothing is global by default
- `export` / `import`; named vs. default exports
- reuse, clear dependencies, smaller files
- in the browser: `<script type="module">`

**Common misconceptions**
- a file's variables are global unless exported

**Interviewer follow-ups**
- "Named or default export: which do you prefer, and why?"

**Verify at:** MDN, "JavaScript modules"

### WEB-LANG-08
**Question:** Compare the CommonJS and ES6 "modules". What are the differences?

> Note for the agent: Changed recently: older material says CommonJS can't `require()` an ES module. Since Node 20.19 / 22.12 it can, without a flag, and since v25.4 the feature is no longer experimental. It still doesn't work for modules with top-level `await`. Accept the older answer, mention the change, and suggest the Node.js docs ("Modules: CommonJS modules" → "Loading ECMAScript modules using require()").

**A good answer covers**
- CommonJS: `require` / `module.exports`, Node's original system, loaded synchronously
- ES modules: `import` / `export`, the language standard, statically analysable
- in Node: `"type": "module"` or `.mjs` / `.cjs`
- mixing them: ESM can import CJS; recent Node versions can also `require()` ESM (without top-level `await`)

**Common misconceptions**
- "they are the same, only the syntax differs"

**Interviewer follow-ups**
- "Which one did your Express project use? How could you tell?"

**Verify at:** Node.js docs, "Modules: ECMAScript modules" and "Modules: CommonJS modules"

### WEB-LANG-09
**Question:** What are higher-order functions in JavaScript?

**A good answer covers**
- a function that takes a function as an argument and / or returns a function
- possible because functions are values
- examples: `map`, `filter`, `addEventListener`, `setTimeout`

**Common misconceptions**
- "a higher-order function is any function inside a function"

**Interviewer follow-ups**
- "Write a function that returns a function."

**Verify at:** MDN Glossary, "First-class function"

### WEB-LANG-10
**Question:** Explain the purpose and functionality of the map function in JavaScript. How does it differ from the filter and reduce functions?

**A good answer covers**
- `map`: same length, each item transformed by the callback
- `filter`: same items, possibly fewer, chosen by a boolean callback
- `reduce`: everything combined into one value, with an accumulator
- all three return something new and don't mutate the original

**Common misconceptions**
- `map` used for side effects only (that's `forEach`)

**Interviewer follow-ups**
- "Get the names of all adults from a list of people. Which methods, in what order?"

**Verify at:** MDN, `Array.prototype.map()`

### WEB-LANG-11
**Question:** How can the filter function be used to selectively extract elements from an array based on a given condition? Provide an example where the filter function is used to create a new array with only the elements that meet the specified criteria.

**A good answer covers**
- the callback returns true / false for each item
- the result is a new array with the items where it returned true
- the original array is unchanged
- a concrete example

**Common misconceptions**
- `filter` returns the first match (that's `find`)

**Interviewer follow-ups**
- "What does `filter` return if nothing matches?"

**Verify at:** MDN, `Array.prototype.filter()`

### WEB-LANG-12
**Question:** What is the role of the reduce function in JavaScript? How can it be used to aggregate or combine the elements of an array into a single value? Provide an example where the reduce function is used to calculate a cumulative sum or find the maximum value in an array.

**A good answer covers**
- callback `(accumulator, current) => newAccumulator`
- the initial value, and why to provide it
- example: sum, maximum
- the "single value" can be an object or array (grouping)

**Common misconceptions**
- reduce can only produce numbers

**Interviewer follow-ups**
- "What happens with `reduce` on an empty array and no initial value?"

**Verify at:** MDN, `Array.prototype.reduce()`

---

## Fetch

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

**Verify at:** MDN, "What is a URL?"

---

## Responsive Design

### WEB-RESP-01
**Question:** What does responsive design do? Why is it important?

**A good answer covers**
- the layout adapts to screen size and device
- one codebase for mobile, tablet, desktop
- usability and accessibility; most traffic is mobile
- SEO / user expectations

**Common misconceptions**
- "responsive = a separate mobile site"

**Interviewer follow-ups**
- "What did you change in your project for small screens?"

**Verify at:** MDN, "Responsive design"

### WEB-RESP-02
**Question:** What is a mobile-first approach?

**A good answer covers**
- write the base styles for small screens first
- add `min-width` media queries for larger screens
- forces focus on the essential content
- smaller screens don't download / override desktop styles

**Common misconceptions**
- "mobile-first means only mobile"

**Interviewer follow-ups**
- "Mobile-first: `min-width` or `max-width` media queries? Why?"

**Verify at:** MDN, "Responsive design"

### WEB-RESP-03
**Question:** How can you test the website's appearance on different screen sizes in the browser?

**A good answer covers**
- DevTools device / responsive mode
- preset devices and custom sizes
- resizing the window
- testing on a real device too

**Common misconceptions**
- (none typical)

**Interviewer follow-ups**
- "What can DevTools device mode *not* tell you?"

**Verify at:** Chrome DevTools docs, "Simulate mobile devices with device mode"

### WEB-RESP-04
**Question:** Can you give some techniques that help to fulfill the responsive design criteria?

**A good answer covers**
- fluid / relative units (%, rem, vw)
- Flexbox and Grid
- media queries
- responsive images (`max-width: 100%`, `srcset`)
- the viewport meta tag
- CSS frameworks' grid systems

**Common misconceptions**
- media queries alone are enough

**Interviewer follow-ups**
- "What does the viewport meta tag do, and what happens without it?"

**Verify at:** MDN, "Responsive design"

### WEB-RESP-05
**Question:** What do media queries do? How do they work?

**A good answer covers**
- apply CSS only when a condition is true (width, orientation, …)
- `@media (min-width: 768px) { … }`
- breakpoints
- later rules override earlier ones when they match

**Common misconceptions**
- media queries change the HTML

**Interviewer follow-ups**
- "Two media queries both match. Which rule wins?"

**Verify at:** MDN, "Using media queries"

### WEB-RESP-06
**Question:** How would you define the Flexbox layout?

**A good answer covers**
- a one-dimensional layout model (row **or** column)
- `display: flex` on the container
- main axis / cross axis; `justify-content` vs. `align-items`
- items can grow, shrink and wrap

**Common misconceptions**
- Flexbox is two-dimensional (that's Grid)

**Interviewer follow-ups**
- "How do you centre something horizontally and vertically?"

**Verify at:** MDN, "Basic concepts of flexbox"

### WEB-RESP-07
**Question:** How can you debug the Flexbox layout in the browser?

**A good answer covers**
- DevTools: the flex badge / overlay on the container
- inspect computed sizes, the box model, gaps
- toggle properties live
- temporary outlines / borders

**Common misconceptions**
- (none typical)

**Interviewer follow-ups**
- "An item won't shrink. What do you check?"

**Verify at:** Chrome DevTools docs, "Inspect and debug CSS flexbox"

### WEB-RESP-08
**Question:** What is the difference between the Flexbox container and the Flexbox item?

**A good answer covers**
- container: the element with `display: flex`; controls direction, wrapping, alignment, gap
- items: its **direct** children; control their own grow / shrink / basis / order / `align-self`
- an element can be both an item and a container

**Common misconceptions**
- grandchildren are flex items too

**Interviewer follow-ups**
- "Where do you put `flex-grow`: on the container or the item?"

**Verify at:** MDN, "Basic concepts of flexbox"

---

## Object Oriented JavaScript

### WEB-OOJS-01
**Question:** What is the difference between the class syntax and the constructor function syntax?

**A good answer covers**
- both create objects that share methods via the prototype
- `class` is mostly syntax over constructor functions + prototypes
- classes: must be called with `new`, not hoisted the same way, body in strict mode
- clearer syntax for inheritance (`extends`, `super`)

**Common misconceptions**
- JS classes work like Java classes (they're prototype-based)

**Interviewer follow-ups**
- "Where are the methods stored in both cases?"

**Verify at:** MDN, "Classes", "Inheritance and the prototype chain"

### WEB-OOJS-02
**Question:** What does the `new` keyword do?

**A good answer covers**
- creates a new empty object
- links it to the constructor's prototype
- runs the constructor with `this` = the new object
- returns the object (unless the constructor returns another object)

**Common misconceptions**
- (none typical; check all steps)

**Interviewer follow-ups**
- "What happens if you call a constructor function without `new`?"

**Verify at:** MDN, `new`

### WEB-OOJS-03
**Question:** What does a `constructor` method do in class syntax? When it is executed?

**A good answer covers**
- initialises a new instance (sets fields from arguments)
- runs once, automatically, on `new ClassName(…)`
- one per class; in a subclass, `super()` must be called before using `this`

**Common misconceptions**
- the constructor must be called manually

**Interviewer follow-ups**
- "What happens in a subclass constructor if you forget `super()`?"

**Verify at:** MDN, `constructor`

### WEB-OOJS-04
**Question:** What are the class methods of a class syntax?

**A good answer covers**
- functions defined in the class body
- shared by all instances (on the prototype)
- called on an instance; `this` is that instance
- `static` methods belong to the class itself

**Common misconceptions**
- each instance gets its own copy of every method

**Interviewer follow-ups**
- "When would you make a method `static`?"

**Verify at:** MDN, "Classes"

### WEB-OOJS-05
**Question:** What are the fields of a class syntax?

**A good answer covers**
- properties declared in the class body (public fields)
- each instance gets its own value
- private fields with `#`
- static fields

**Common misconceptions**
- fields are shared between instances like methods

**Interviewer follow-ups**
- "What does `#` in front of a field name mean?"

**Verify at:** MDN, "Public class fields", "Private properties"

### WEB-OOJS-06
**Question:** What is inheritance in the context of Javascript objects?

**A good answer covers**
- an object can use properties / methods of another through the prototype chain
- lookup goes up the chain until found or `null`
- with classes: `extends` sets up the chain
- reuse and specialisation

**Common misconceptions**
- properties are copied into the child

**Interviewer follow-ups**
- "What does the prototype chain look like for an array?"

**Verify at:** MDN, "Inheritance and the prototype chain"

### WEB-OOJS-07
**Question:** What does the `extends` keyword do?

**A good answer covers**
- creates a subclass of another class
- the subclass inherits the parent's methods
- `super(...)` calls the parent constructor; `super.method()` the parent method
- methods can be overridden

**Common misconceptions**
- a class can extend several classes

**Interviewer follow-ups**
- "How do you call the parent's version of an overridden method?"

**Verify at:** MDN, `extends`, `super`

---

## Express

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

**Verify at:** Express docs, "Serving static files in Express"

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

**Verify at:** Express docs, "Routing" (Route parameters)

---

## REST and CRUD

### WEB-REST-01
**Question:** Can you name some typical HTTP response codes and their meaning?

**A good answer covers**
- 2xx success: 200 OK, 201 Created, 204 No Content
- 3xx redirect: 301, 304
- 4xx client error: 400, 401, 403, 404
- 5xx server error: 500
- the meaning of the class (first digit)

**Common misconceptions**
- 401 and 403 mean the same

**Interviewer follow-ups**
- "Which code for a successful DELETE? For creating a new item?"

**Verify at:** MDN, "HTTP response status codes"

### WEB-REST-02
**Question:** Can you name some typical HTTP request/response headers and their meaning?

**A good answer covers**
- `Content-Type`, `Accept`
- `Authorization`
- `Cache-Control`
- `Set-Cookie` / `Cookie`
- CORS headers (`Access-Control-Allow-Origin`)

**Common misconceptions**
- headers are part of the body

**Interviewer follow-ups**
- "Which header tells the server that your body is JSON?"

**Verify at:** MDN, "HTTP headers"

### WEB-REST-03
**Question:** What are the common HTTP methods used in web development, and what are their respective purposes?

**A good answer covers**
- GET read, POST create, PUT replace, PATCH partial update, DELETE remove
- mapping to CRUD
- safe (GET) and idempotent (GET, PUT, DELETE) methods

**Common misconceptions**
- POST is the only way to send data

**Interviewer follow-ups**
- "Which of these are idempotent, and what does that mean?"

**Verify at:** MDN, "HTTP request methods"

### WEB-REST-04
**Question:** How does the GET method differ from the POST method? Explain when it is appropriate to use each method. Which one uses the request body to receive data?

**A good answer covers**
- GET: read, data only in the URL (path / query), cacheable, bookmarkable, no side effects
- POST: create / trigger an action, data in the **body**
- GET shouldn't change server state
- sensitive data doesn't belong in a URL

**Common misconceptions**
- POST is "secure" because the data isn't in the URL (it still needs HTTPS)

**Interviewer follow-ups**
- "Why shouldn't a GET request delete something?"

**Verify at:** MDN, "GET", "POST"

### WEB-REST-05
**Question:** Explain the use of the PATCH method in HTTP. How does it differ from the PUT method, and when should it be used to update a resource?

**A good answer covers**
- PUT replaces the whole resource with the body
- PATCH changes only the fields that were sent
- PUT is idempotent; PATCH isn't necessarily
- missing fields: PUT removes / resets them, PATCH leaves them

**Common misconceptions**
- PUT and PATCH are interchangeable

**Interviewer follow-ups**
- "You PUT a user with only an email. What should happen to the name?"

**Verify at:** MDN, "PATCH", "PUT"

### WEB-REST-06
**Question:** How can the DELETE method be used to remove a resource from a server? Explain how the DELETE method works and any considerations for handling resource deletion.

**A good answer covers**
- `DELETE /resource/:id`
- typical responses: 204 No Content (or 200 with a body), 404 if not found
- idempotent: deleting twice has the same effect
- considerations: authorisation, related data, soft delete, confirmation in the UI

**Common misconceptions**
- DELETE needs a request body

**Interviewer follow-ups**
- "What should a second DELETE for the same ID return?"

**Verify at:** MDN, "DELETE"

### WEB-REST-07
**Question:** What does the REST architecture mean? What are the REST Constraints?

**A good answer covers**
- an architectural style for APIs built around resources
- constraints: client-server, stateless, cacheable, uniform interface, layered system, (optional) code on demand
- resources identified by URLs; manipulated through representations (JSON)
- HTTP methods express the action

**Common misconceptions**
- "REST = any API that returns JSON"

**Interviewer follow-ups**
- "What does 'stateless' mean for your server?"

**Verify at:** Roy Fielding's dissertation ch. 5; MDN Glossary, "REST"

### WEB-REST-08
**Question:** What does a URL's path represent in a REST architecture? Show an example of the `recipe` resource's CRUD operations. Define the HTTP method and a corresponding path for each CRUD operation.

**A good answer covers**
- the path names a resource (nouns, not verbs)
- `GET /recipes`, `GET /recipes/:id`
- `POST /recipes`
- `PUT` / `PATCH /recipes/:id`
- `DELETE /recipes/:id`

**Common misconceptions**
- verbs in paths (`/getRecipes`, `/deleteRecipe`)

**Interviewer follow-ups**
- "How would you model a recipe's ingredients in the URL?"

**Verify at:** MDN Glossary, "REST"

### WEB-REST-09
**Question:** How do you handle form submissions using JavaScript? Explain the process of capturing form data and preventing the default form submission behavior.

**A good answer covers**
- listen to the form's `submit` event (not the button's click)
- `event.preventDefault()` stops the page reload
- read values (inputs, or `new FormData(form)`)
- send them with `fetch`, then update the UI

**Common misconceptions**
- listening to the button click is the same

**Interviewer follow-ups**
- "Why `submit` on the form rather than `click` on the button?"

**Verify at:** MDN, "HTMLFormElement: submit event", `FormData`

### WEB-REST-10
**Question:** Explain the required elements necessary to define a form in HTML.

**A good answer covers**
- `<form>` (with `action` / `method` when not handled by JS)
- input elements with `name`
- labels
- a submit button

**Common misconceptions**
- inputs without `name` are submitted

**Interviewer follow-ups**
- "What does a `<button>` inside a form do by default?"

**Verify at:** MDN, "Your first form"

### WEB-REST-11
**Question:** What is the purpose of the required attribute in HTML form elements? How does it enforce mandatory input fields and prevent form submission without the required information?

**A good answer covers**
- marks a field as mandatory
- the browser blocks submit and shows a message
- part of built-in constraint validation
- client-side only: the server must still validate

**Common misconceptions**
- `required` is enough validation

**Interviewer follow-ups**
- "Why do you still need validation on the server?"

**Verify at:** MDN, "Client-side form validation"

### WEB-REST-12
**Question:** Explain the different types of form input fields available in HTML. How do input types like text, number, email, checkbox, and radio buttons differ, and how are they used in forms?

**A good answer covers**
- text, number, email (built-in validation, mobile keyboards)
- checkbox: independent on / off (`checked`)
- radio: one choice in a group (same `name`)
- others: password, date, select, textarea
- values arrive as strings

**Common misconceptions**
- a number input gives you a number value

**Interviewer follow-ups**
- "How do you group radio buttons so only one can be selected?"

**Verify at:** MDN, `<input>` types

### WEB-REST-13
**Question:** Can you explain the purpose of the name attribute in the context of form submission?

**A good answer covers**
- the key under which the value is sent
- only named fields are submitted
- groups radio buttons
- used by `FormData`

**Common misconceptions**
- `id` and `name` do the same thing

**Interviewer follow-ups**
- "What's the difference between `id` and `name` on an input?"

**Verify at:** MDN, `<input>` (name attribute)

### WEB-REST-14
**Question:** Can you explain how we can connect a label tag to a form element?

**A good answer covers**
- `<label for="id">` matching the input's `id`
- or wrap the input inside the label
- clicking the label focuses the input
- accessibility: screen readers read the label

**Common misconceptions**
- placeholder replaces a label

**Interviewer follow-ups**
- "Why is a placeholder not a replacement for a label?"

**Verify at:** MDN, `<label>`

### WEB-REST-15
**Question:** How can you dynamically manipulate or modify form elements using JavaScript? Explain how to add or remove form fields dynamically based on user interaction or specific conditions.

**A good answer covers**
- create inputs with `createElement`, set attributes, append them
- remove with `remove()`
- change properties: `disabled`, `value`, `required`
- react to events (change, input) to decide what to show

**Common misconceptions**
- (none typical)

**Interviewer follow-ups**
- "How would you show an extra field only when a checkbox is ticked?"

**Verify at:** MDN, "Introduction to the DOM"

### WEB-REST-16
**Question:** How can you convert form data into a format that can be easily transmitted or processed by the server?

**A good answer covers**
- `new FormData(form)`
- `Object.fromEntries(formData)` gives a plain object
- `JSON.stringify` + `Content-Type: application/json`
- or URL-encoded / multipart (for files)
- convert types where needed (numbers, booleans)

**Common misconceptions**
- `FormData` can be passed to `JSON.stringify` directly

**Interviewer follow-ups**
- "How do you send a file to the server?"

**Verify at:** MDN, `FormData`, `Object.fromEntries()`

---

## React

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

**Verify at:** react.dev, "Updating Objects in State", "Updating Arrays in State"

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

**Verify at:** react.dev, "Conditional Rendering"

### WEB-REACT-17
**Question:** What is the difference between a controlled and uncontrolled input element in React?

**A good answer covers**
- controlled: `value` comes from state, `onChange` updates the state; React is the source of truth
- uncontrolled: the DOM keeps the value; read it when needed (ref or `FormData`)
- controlled gives live validation / formatting
- `defaultValue` vs. `value`

**Common misconceptions**
- `value` without `onChange` (read-only input warning)

**Interviewer follow-ups**
- "When is an uncontrolled input the simpler choice?"

**Verify at:** react.dev, `<input>` (Controlling an input with a state variable)

### WEB-REACT-18
**Question:** How can you get the current input values from a form that contains uncontrolled input elements?

**A good answer covers**
- in the submit handler: `new FormData(event.target)`
- `Object.fromEntries(formData)` for a plain object
- or refs (`useRef`) to read `.value`
- inputs need `name`

**Common misconceptions**
- you have to use state for every input

**Interviewer follow-ups**
- "Why does `FormData` need the `name` attribute?"

**Verify at:** react.dev, `<form>`; MDN, `FormData`

### WEB-REACT-19
**Question:** How can you connect a label element to an input element in React?

**A good answer covers**
- `htmlFor` instead of `for`, matching the input's `id`
- or wrap the input in the label
- `useId()` for unique IDs in reusable components

**Common misconceptions**
- `for` works the same in JSX

**Interviewer follow-ups**
- "Your input component is used three times on a page. How do you keep the IDs unique?"

**Verify at:** react.dev, `useId`

### WEB-REACT-20
**Question:** How can you create a select input element in React? How does it differ from the html's select tag? Can you show an example of a controlled and an uncontrolled select element with setting a default value?

**A good answer covers**
- `<select>` with `<option>` children, often generated with `map`
- React uses `value` / `defaultValue` on the `<select>`, not `selected` on an option
- controlled: `value={state}` + `onChange`
- uncontrolled: `defaultValue="…"`, read on submit

**Common misconceptions**
- `selected` on an `<option>` is the React way

**Interviewer follow-ups**
- "How do you add a 'Show all' option to a filter select?"

**Verify at:** react.dev, `<select>`

### WEB-REACT-21
**Question:** Explain how a proxy works during React development. How can you tell the Vite dev server to proxy the requests to your backend? What kind of URLs do you have to use in the fetch in your JS code, if you want to use the proxy?

**A good answer covers**
- the frontend dev server forwards certain requests to the backend server
- avoids CORS problems in development (same origin from the browser's view)
- Vite: `server.proxy` in `vite.config.js`, e.g. `'/api': 'http://localhost:8080'`
- fetch with **relative** URLs (`/api/...`), not the backend's full address
- only in development; production needs its own setup

**Common misconceptions**
- the proxy also works in the production build

**Interviewer follow-ups**
- "You fetch `http://localhost:8080/api/x` and get a CORS error. Why?"

**Verify at:** Vite docs, "server.proxy"

### WEB-REACT-22
**Question:** What is the difference between statements and expressions in Javascript? Why is it important when working with JSX?

**A good answer covers**
- an expression produces a value (`a + b`, `fn()`, ternary)
- a statement does something (`if`, `for`, `let`)
- inside `{ }` in JSX only expressions are allowed
- so use ternary / `&&` / `map` instead of `if` / `for` in JSX

**Common misconceptions**
- an `if` can go inside `{ }`

**Interviewer follow-ups**
- "Why does `map` work inside JSX but `for` doesn't?"

**Verify at:** MDN, "Expressions and operators", "Statements and declarations"

---

## Testing Basics

### WEB-TEST-01
**Question:** What is a test case?

**A good answer covers**
- one specific scenario: given input / state, expected result
- runs automatically and gives pass / fail
- named after the behaviour it checks

**Common misconceptions**
- a test case = a test file

**Interviewer follow-ups**
- "Give me three test cases for a function that checks a password."

**Verify at:** Vitest docs, "Getting Started"

### WEB-TEST-02
**Question:** What are the advantages of writing unit tests?

**A good answer covers**
- catch bugs early, close to where they are
- safe refactoring (regression protection)
- document expected behaviour
- push towards smaller, testable functions
- fast feedback

**Common misconceptions**
- "tests prove there are no bugs"

**Interviewer follow-ups**
- "When did a test save you from a bug?"

**Verify at:** Martin Fowler, "Unit Test" (martinfowler.com)

### WEB-TEST-03
**Question:** What is an assertion? Give some examples.

**A good answer covers**
- a statement that checks an expected condition and fails the test if it is false
- `expect(x).toBe(…)`, `toEqual`, `toContain`, `toThrow`, `toBeTruthy`
- a test can have several, but ideally checks one behaviour

**Common misconceptions**
- (none typical)

**Interviewer follow-ups**
- "How do you assert that a function throws?"

**Verify at:** Vitest docs, "expect"

### WEB-TEST-04
**Question:** What is the arrange/act/assert pattern?

**A good answer covers**
- arrange: set up input and state
- act: call the code under test
- assert: check the result
- makes tests readable and focused

**Common misconceptions**
- several act steps in one test

**Interviewer follow-ups**
- "Point out the three parts in one of your tests."

**Verify at:** (no single authoritative source; judge by the rubric and the student's own example, don't search)

### WEB-TEST-05
**Question:** What is code coverage? Why is it used?

**A good answer covers**
- the share of code (lines, branches, functions) executed by the tests
- shows untested parts
- high coverage ≠ good tests (assertions may be weak)
- branch coverage is stricter than line coverage

**Common misconceptions**
- 100% coverage means bug-free

**Interviewer follow-ups**
- "How can you have 100% coverage and still miss a bug?"

**Verify at:** Vitest docs, "Coverage"

### WEB-TEST-06
**Question:** How do you test asynchronous code with Vitest?

**A good answer covers**
- make the test function `async` and `await` the code
- or return the Promise
- `expect(promise).resolves` / `.rejects`
- mocking / faking slow dependencies (fetch, timers)

**Common misconceptions**
- forgetting `await`, so the test passes before the assertion runs

**Interviewer follow-ups**
- "Your async test always passes, even when it shouldn't. What's the likely cause?"

**Verify at:** Vitest docs, "expect" (resolves / rejects)

### WEB-TEST-07
**Question:** What is `setup` & `teardown` in Vitest?

**A good answer covers**
- code run before / after tests: `beforeEach`, `afterEach`, `beforeAll`, `afterAll`
- setup prepares a fresh state; teardown cleans up
- keeps tests independent

**Common misconceptions**
- tests can depend on the order they run in

**Interviewer follow-ups**
- "Why `beforeEach` instead of `beforeAll` for resetting data?"

**Verify at:** Vitest docs, "Setup and Teardown"

### WEB-TEST-08
**Question:** Give an example when you would use in Vitest's the `toBe` & `toEqual` assertions.

**A good answer covers**
- `toBe`: strict identity (`Object.is`); for primitives or the same object reference
- `toEqual`: deep equality of content; for objects and arrays
- `expect([1]).toBe([1])` fails, `toEqual` passes

**Common misconceptions**
- they are interchangeable

**Interviewer follow-ups**
- "Which one for checking a function's returned array?"

**Verify at:** Vitest docs, "expect" (toBe, toEqual)

---

## Firebase Realtime Database

### WEB-FBDB-01
**Question:** What is Firebase Realtime Database? Explain the key features and advantages of the Realtime Database as a NoSQL database solution.

**A good answer covers**
- a cloud-hosted NoSQL database storing one JSON tree
- real-time sync to connected clients
- access via SDKs or a REST API
- security rules instead of your own backend
- trade-offs: limited querying, data modelling matters

**Common misconceptions**
- it works like a SQL database with tables and joins

**Interviewer follow-ups**
- "What would you lose compared with a SQL database?"

**Verify at:** Firebase docs, "Firebase Realtime Database"

### WEB-FBDB-02
**Question:** Explain the concept of storing data in a Realtime Database. How does a Realtime Database store data in a JSON tree?

**A good answer covers**
- all data is one big JSON object
- every node has a path / URL
- lists usually as objects keyed by generated IDs, not arrays
- reading a node returns all its children

**Common misconceptions**
- arrays are the natural way to store lists there

**Interviewer follow-ups**
- "Why are generated push keys used instead of array indexes?"

**Verify at:** Firebase docs, "Structure your database"

### WEB-FBDB-03
**Question:** How can you access the Realtime Database with a REST API? What do the typical CRUD operations look like?

**A good answer covers**
- any path + `.json` is an endpoint
- GET read, PUT write / replace, POST add with a generated key, PATCH update fields, DELETE remove
- authentication via a token parameter
- query parameters for ordering / filtering

**Common misconceptions**
- forgetting `.json` at the end of the URL

**Interviewer follow-ups**
- "What does POST return, and how do you use it?"

**Verify at:** Firebase docs, "Realtime Database REST API"

### WEB-FBDB-04
**Question:** How the Realtime Database Security Rules can help to define the structure of the stored data (validation) when the data can be read from or written to?

**A good answer covers**
- rules per path: `.read`, `.write`, `.validate`
- conditions can use `auth`, the new data, existing data
- `.validate` enforces types / required fields
- rules cascade down the tree
- test-mode (open) rules are only for development

**Common misconceptions**
- frontend validation is enough

**Interviewer follow-ups**
- "How would you allow users to write only their own data?"

**Verify at:** Firebase docs, "Understand Firebase Realtime Database Security Rules"

### WEB-FBDB-05
**Question:** Why is it a problem if the data is deeply nested? What techniques can solve this issue?

**A good answer covers**
- reading a node downloads its whole subtree
- access rules cascade, so access is hard to limit
- flatten / denormalise: separate top-level nodes, linked by IDs
- duplicate data deliberately where it makes reads cheap

**Common misconceptions**
- nesting is free, like in a local JS object

**Interviewer follow-ups**
- "Design the data for users and their posts. Nested or flat?"

**Verify at:** Firebase docs, "Structure your database"

---

## Firebase Authentication

### WEB-AUTH-01
**Question:** Why authentication is needed for a web application?

**A good answer covers**
- know who the user is
- personalise data and protect private data
- basis for authorisation (who may do what)
- accountability / auditing

**Common misconceptions**
- (none typical)

**Interviewer follow-ups**
- "Which parts of your project needed a signed-in user, and why?"

**Verify at:** Firebase docs, "Firebase Authentication"

### WEB-AUTH-02
**Question:** What are the key functionalities of an authentication system?

**A good answer covers**
- sign up, sign in, sign out
- keeping the session / persistence
- password handling (hashing, reset), email verification
- identity providers (Google, …)
- account management

**Common misconceptions**
- passwords are stored as plain text

**Interviewer follow-ups**
- "Why should you never build password storage yourself?"

**Verify at:** OWASP, "Authentication Cheat Sheet"

### WEB-AUTH-03
**Question:** How does the server know that the client is successfully authenticated?

**A good answer covers**
- after sign-in the client gets a token (e.g. an ID token / JWT) or a session cookie
- the client sends it with each request (e.g. `Authorization` header)
- the server verifies it (signature, expiry)
- tokens expire and are refreshed

**Common misconceptions**
- the server remembers that the browser logged in, with nothing sent

**Interviewer follow-ups**
- "What happens when the token expires?"

**Verify at:** Firebase docs, "Verify ID Tokens"; jwt.io introduction

### WEB-AUTH-04
**Question:** What is the difference between Authentication and Authorization?

**A good answer covers**
- authentication: who you are
- authorisation: what you're allowed to do
- authentication comes first
- example from their project

**Common misconceptions**
- they are the same thing

**Interviewer follow-ups**
- "Which status code fits each failure: not logged in vs. not allowed?"

**Verify at:** MDN Glossary, "Authentication", "Authorization"

### WEB-AUTH-05
**Question:** How can you initialize the Firebase Authentication SDK?

**A good answer covers**
- register a web app → config object
- `initializeApp(config)`
- `getAuth(app)` returns the auth instance
- enable the sign-in providers in the console

**Common misconceptions**
- the config values are secret passwords

**Interviewer follow-ups**
- "Is it a problem that the Firebase config is visible in the browser? Why or why not?"

**Verify at:** Firebase docs, "Get Started with Firebase Authentication on Websites"

### WEB-AUTH-06
**Question:** How the Firebase Realtime Database Security Rules can enforce authorization?

**A good answer covers**
- rules can check `auth` (signed in) and `auth.uid`
- e.g. `".read": "auth != null"`; per-user paths with `$uid === auth.uid`
- enforced on the server, so a modified client can't bypass them
- UI hiding is not security

**Common misconceptions**
- hiding a page in React protects the data

**Interviewer follow-ups**
- "A user opens DevTools and calls your database directly. What stops them?"

**Verify at:** Firebase docs, "Realtime Database Security Rules" (auth variable)

### WEB-AUTH-07
**Question:** What kind of different authentication providers are supported by Firebase? Can you give some examples?

**A good answer covers**
- email / password, email link
- federated: Google, Facebook, GitHub, Apple, Microsoft, X
- phone number
- anonymous

**Common misconceptions**
- (none typical)

**Interviewer follow-ups**
- "Why might a user prefer signing in with Google?"

**Verify at:** Firebase docs, "Firebase Authentication"

---

## Web Applications

### WEB-APP-01
**Question:** Explain the concept of React Router. How does it enable client-side routing in React.js applications and facilitate the creation of multi-page-like experiences?

**A good answer covers**
- maps URLs to components without a full page reload
- uses the History API; the server sends one HTML page
- `<Link>` instead of `<a>`, route parameters, nested routes
- back / forward and bookmarking still work

**Common misconceptions**
- each route is a separate HTML file

**Interviewer follow-ups**
- "Why does reloading a sub-page on a static host sometimes give a 404?"

**Verify at:** React Router docs

### WEB-APP-02
**Question:** Why is it needed to `build` a React application? What does this build step do?

**A good answer covers**
- browsers don't understand JSX / modules as written
- build compiles JSX, bundles files, minifies, optimises assets
- output: static HTML / CSS / JS (e.g. a `dist` folder)
- environment-specific values are baked in

**Common misconceptions**
- you deploy the `src` folder

**Interviewer follow-ups**
- "What's in your `dist` folder after building?"

**Verify at:** Vite docs, "Building for Production"

### WEB-APP-03
**Question:** What is the difference between local development (using a dev server, like Vite) and production deployment?

**A good answer covers**
- dev: fast rebuilds, hot reload, source maps, dev proxy, verbose errors
- prod: optimised static build served by a host / CDN
- different config / environment variables
- the dev proxy doesn't exist in production

**Common misconceptions**
- the dev server is fine for production

**Interviewer follow-ups**
- "Your app works locally but API calls fail after deploy. What do you check?"

**Verify at:** Vite docs, "Building for Production"

### WEB-APP-04
**Question:** How can you deploy a Firebase application?

**A good answer covers**
- Firebase CLI: login, `firebase init` (hosting), set the public / build folder
- build the app first
- `firebase deploy`
- single-page-app rewrite to `index.html`
- deploy rules too

**Common misconceptions**
- deploying the source folder instead of the build output

**Interviewer follow-ups**
- "Why does an SPA need the rewrite rule?"

**Verify at:** Firebase docs, "Get started with Firebase Hosting"

### WEB-APP-05
**Question:** What are React Contexts? Which use cases are they suitable for?

**A good answer covers**
- share a value with a whole subtree without passing props through every level
- `createContext`, a Provider, `useContext`
- good for: current user, theme, language, app-wide settings
- not a replacement for all props; every consumer re-renders when the value changes

**Common misconceptions**
- "Context is a state manager by itself" (it carries state you keep elsewhere)

**Interviewer follow-ups**
- "When is passing props still the better choice?"

**Verify at:** react.dev, "Passing Data Deeply with Context"
