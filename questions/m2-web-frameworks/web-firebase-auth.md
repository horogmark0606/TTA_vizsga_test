# web-firebase-auth

Module 2 · Web Frameworks · workbook section "Firebase Authentication" (WEB-AUTH-01 – WEB-AUTH-07).
Source: the module's Tech Interview Workbook. Rubrics drafted 2026-10-19; flagged items reviewed by the mentor, full review in progress.
Rubrics are for the agent only: never show them or turn them into a model answer (see AGENTS.md).

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

**Practised in:** Set up Authentication with Firebase

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

**Practised in:** Set up Authentication with Firebase, My Secrets

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

**Practised in:** My Secrets

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

**Practised in:** My Secrets, Freestyle Firebase Project, Part 2

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

**Practised in:** Set up Authentication with Firebase

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

**Practised in:** Employee Madness Firebase, Freestyle Firebase Project, Part 2

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

**Practised in:** Set up Authentication with Firebase, Employee Madness Firebase

**Verify at:** Firebase docs, "Firebase Authentication"
