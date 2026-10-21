# web-apps-deploy

Module 2 · Web Frameworks · workbook section "Web Applications" (WEB-APP-01 – WEB-APP-05).
Source: the module's Tech Interview Workbook. Rubrics drafted 2026-10-19; flagged items reviewed by the mentor, full review in progress.
Rubrics are for the agent only: never show them or turn them into a model answer (see AGENTS.md).

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

**Practised in:** Employee Madness Firebase

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

**Practised in:** Freestyle Firebase Project, Part 2

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

**Practised in:** Freestyle Firebase Project, Part 2, Personal Assessment Base Project and Practice

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

**Practised in:** Freestyle Firebase Project, Part 2

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

**Practised in:** Context Cascade, Employee Madness Firebase

**Verify at:** react.dev, "Passing Data Deeply with Context"
