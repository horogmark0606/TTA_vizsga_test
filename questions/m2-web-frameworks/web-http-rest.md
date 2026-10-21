# web-http-rest

Module 2 · Web Frameworks · workbook section "REST and CRUD" (WEB-REST-01 – WEB-REST-08).
Source: the module's Tech Interview Workbook. Rubrics drafted 2026-10-19; flagged items reviewed by the mentor, full review in progress.
Rubrics are for the agent only: never show them or turn them into a model answer (see AGENTS.md).

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

**Practised in:** Movie Data Server, Use, Yet Another Online Shop

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

**Practised in:** Yet Another Online Shop

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

**Practised in:** Your very own TODO list, Use, Movie editor, Yet Another Online Shop

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

**Practised in:** Yet Another Online Shop, More on fetch the countries

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

**Practised in:** Use, Movie editor

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

**Practised in:** Use

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

**Practised in:** Favorite data editor

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

**Practised in:** Use, Favorite data editor

**Verify at:** MDN Glossary, "REST"
