# web-firebase-db

Module 2 · Web Frameworks · workbook section "Firebase Realtime Database" (WEB-FBDB-01 – WEB-FBDB-05).
Source: the module's Tech Interview Workbook. Rubrics drafted 2026-10-19; flagged items reviewed by the mentor, full review in progress.
Rubrics are for the agent only: never show them or turn them into a model answer (see AGENTS.md).

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

**Practised in:** Firebase Real Time Database Quickstart

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

**Practised in:** Firebase Real Time Database Quickstart, Freestyle Firebase Project, Part 1

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

**Practised in:** Firebase Real Time Database Quickstart, World traveler, Personal Assessment Base Project and Practice

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

**Practised in:** Firebase Real Time Database Quickstart

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

**Practised in:** Freestyle Firebase Project, Part 1, Employee Madness Firebase

**Verify at:** Firebase docs, "Structure your database"
