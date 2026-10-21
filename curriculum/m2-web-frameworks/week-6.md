# Web Frameworks — Authentication

> Project cards for Week 6 — Authentication. Concept level only: no project descriptions,
> tasks or solutions. Question IDs point to topics in `questions/index.yaml`.
> Status: drafted 2026-10-19; mentor review in progress.

## Week 6 — Authentication

### WEB · Set up Authentication with Firebase (solo, week 6)

**Concepts to understand**
- Registering a web app and initialising Firebase in a React project.
- The Auth SDK: getting the auth instance.
- Enabling the email / password provider.
- Sign-up and sign-in calls, and showing success and error messages.
- Listening to auth state changes to know who is signed in.

**Typical pitfalls**
- Config values committed to the repo without understanding which ones are secret.
- Showing raw error codes to the user.

**Explain-your-own-code prompts**
- "How does your app find out that the user is signed in? Who tells it?"
- "What happens, step by step, when sign-up fails?"

**Related questions:** WEB-AUTH-01, WEB-AUTH-02, WEB-AUTH-05, WEB-AUTH-07

### WEB · My Secrets (solo, week 6)

**Concepts to understand**
- Working in an existing React app: reading its navigation before changing it.
- Sign up, sign in and sign out with the Auth SDK.
- Storing the current user in app state, and persisting the login across reloads.
- Changing the view based on auth state; protecting a page.
- Form validation: matching passwords, live password-strength feedback.

**Typical pitfalls**
- The "protected" page is only hidden in the menu, not really protected.
- A flash of the wrong page while auth state is still loading.

**Explain-your-own-code prompts**
- "A signed-out user opens the secret page directly. What exactly stops them?"
- "Reload the page while signed in. How does your app know who you are?"

**Related questions:** WEB-AUTH-02, WEB-AUTH-03, WEB-AUTH-04, WEB-REACT-16, WEB-REST-09

### WEB · Employee Madness Firebase (solo, week 6)

**Concepts to understand**
- Getting an existing full-stack app running: environment variables, database rules, seed data.
- Several sign-in providers (Google and email / password).
- Rules that allow access only to authenticated users.
- Filtering, searching, sorting and pagination of a list.
- A new entity and a relation between entities (who uses which equipment).
- A route with a dynamic segment.
- React Context for shared app state.

**Typical pitfalls**
- Pagination and filters that don't work together.
- Environment variables missing or committed.

**Explain-your-own-code prompts**
- "Where does the app read its configuration from? Why not hard-code it?"
- "How did you connect equipment to employees in the data?"
- "Filter, then go to page 2. What should happen, and what does your code do?"

**Related questions:** WEB-AUTH-06, WEB-AUTH-07, WEB-APP-01, WEB-APP-05, WEB-FBDB-05

### WEB · Freestyle Firebase Project, Part 2 (team, week 6)

**Concepts to understand**
- Replanning: adding features to an existing product.
- Sign up and sign in; protected pages with redirect to login.
- Security rules that protect data at the database level, not just in the UI.
- Building and deploying the app.

**Typical pitfalls**
- Protection only in the UI: the data is still open in the database.
- The deployed app behaves differently from the local one (config, routes).

**Explain-your-own-code prompts**
- "Someone skips your UI and calls the database directly. What stops them?"
- "What happens during the build, and what actually gets deployed?"

**Related questions:** WEB-AUTH-04, WEB-AUTH-06, WEB-APP-02, WEB-APP-03, WEB-APP-04
