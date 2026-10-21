# Web Frameworks — REST

> Project cards for Week 3 — REST. Concept level only: no project descriptions,
> tasks or solutions. Question IDs point to topics in `questions/index.yaml`.
> Status: drafted 2026-10-19; mentor review in progress.

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
