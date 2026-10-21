# web-js-es6

Module 2 · Web Frameworks · workbook section "JavaScript Language Features" (WEB-LANG-01 – WEB-LANG-08).
Source: the module's Tech Interview Workbook. Rubrics drafted 2026-10-19; flagged items reviewed by the mentor, full review in progress.
Rubrics are for the agent only: never show them or turn them into a model answer (see AGENTS.md).

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

**Practised in:** (no project; theory only)

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

**Practised in:** (no project; theory only)

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

**Practised in:** File handling

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

**Practised in:** Registration form

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

**Practised in:** Your very own TODO list

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

**Practised in:** (no project; theory only)

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

**Practised in:** File handling, Your very own TODO list

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

**Practised in:** Rookie Homecook

**Verify at:** Node.js docs, "Modules: ECMAScript modules" and "Modules: CommonJS modules"
