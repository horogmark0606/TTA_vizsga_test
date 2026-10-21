# pb-js-specialties

Module 1 · Programming Basics · workbook section "JavaScript — Language Specialties" (PB-LANG-01 – PB-LANG-06).
Source: the module's Tech Interview Workbook. Rubrics drafted 2026-10-19; flagged items reviewed by the mentor, full review in progress.
Rubrics are for the agent only: never show them or turn them into a model answer (see AGENTS.md).

### PB-LANG-01
**Question:** Elaborate on the differences between value and reference data types in JavaScript, specifically in relation to objects and primitives.

**A good answer covers**
- primitives are copied by value
- objects/arrays: the variable holds a reference; copying the variable copies the reference
- two variables can point to the same object, so a change is visible through both
- `===` on objects compares references
- how to make a (shallow) copy

**Common misconceptions**
- `const b = a` copies an array

**Interviewer follow-ups**
- "Why did changing one row of your board change other rows?"

**Practised in:** Take me to a nice place, Tic-tac-toe-console, Boring buses, Memorize numbers, Battleship.js (console), Secure ERP

**Verify at:** MDN, "JavaScript data types and data structures"

### PB-LANG-02
**Question:** Discuss the concept of mutability and immutability in objects, arrays, and primitives, and explain why it is important to understand when working with data structures in JavaScript.

**A good answer covers**
- primitives are immutable (operations make new values)
- objects/arrays are mutable by default
- methods that mutate vs. return new
- `const` does not make an object immutable
- why it matters: hidden side effects, bugs in shared data

**Common misconceptions**
- `const arr = []` means the array can't change

**Interviewer follow-ups**
- "How do you update one item in an array without changing the original?"

**Practised in:** Become a coder, Vacation expenses, Tic-tac-toe-console, Functional trio, Secure ERP, More on product list

**Verify at:** MDN, "Mutable" (Glossary), `const`

### PB-LANG-03
**Question:** Is `null` considered an object or a primitive in JavaScript?

**A good answer covers**
- `null` is a primitive
- `typeof null === 'object'` is a historical bug
- `null` = intentionally "no value"

**Common misconceptions**
- "`null` is an object because `typeof` says so"

**Interviewer follow-ups**
- "How do you check whether a value is `null`?"

**Practised in:** Take me to a nice place

**Verify at:** MDN, `null`, `typeof`

### PB-LANG-04
**Question:** What does `undefined` represent in JavaScript?

**A good answer covers**
- a value that hasn't been assigned
- where it shows up: unassigned variable, missing property, missing argument, function without `return`
- difference from `null` (intentional absence)

**Common misconceptions**
- `undefined` and "not declared" are the same (accessing an undeclared variable throws)

**Interviewer follow-ups**
- "What does a function without `return` give back?"

**Practised in:** Hello Functions!

**Verify at:** MDN, `undefined`

### PB-LANG-05
**Question:** When would you use `var`, `let`, and `const` in JavaScript?

**A good answer covers**
- `const` by default; `let` when the variable will be reassigned
- `var`: function-scoped, hoisted, avoided in modern code
- `let` / `const` are block-scoped
- `const` prevents reassignment, not mutation

**Common misconceptions**
- `const` objects can't be changed

**Interviewer follow-ups**
- "Why does your code use `let` here and `const` there?"

**Practised in:** Text Adventure

**Verify at:** MDN, `let`, `const`, `var`

### PB-LANG-06
**Question:** Explain the concept of hoisting in JavaScript.

**A good answer covers**
- declarations are processed before the code runs
- function declarations can be called before they appear
- `var` is hoisted with `undefined`
- `let` / `const` are hoisted but not usable before the line (temporal dead zone)

**Common misconceptions**
- "the code is physically moved to the top"

**Interviewer follow-ups**
- "What happens if you use a `let` variable one line before declaring it?"

**Practised in:** Hello Functions!

**Verify at:** MDN, "Hoisting" (Glossary)
