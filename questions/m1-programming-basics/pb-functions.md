# pb-functions

Module 1 · Programming Basics · workbook section "Function Basics" (PB-FN-01 – PB-FN-06).
Source: the module's Tech Interview Workbook. Rubrics drafted 2026-10-19; flagged items reviewed by the mentor, full review in progress.
Rubrics are for the agent only: never show them or turn them into a model answer (see AGENTS.md).
Extra care topic: go gradual and concrete.

### PB-FN-01
**Question:** What is a function in JavaScript? Explain its purpose and how it is used in programming.

**A good answer covers**
- a named, reusable block of code
- takes input (parameters), can give back output (`return`)
- reasons: reuse, readability, splitting a problem into parts, testability
- defining vs. calling

**Common misconceptions**
- "a function must return something"

**Interviewer follow-ups**
- "Show me a function from your project. Why is it a function and not inline code?"

**Practised in:** Hangman, Hello Functions!, Password validator, Take me to a nice place, Tic-tac-toe-console, Functional calculator, Memorize numbers, Battleship.js (console)

**Verify at:** MDN, "Functions" (Guide)

### PB-FN-02
**Question:** Describe the different syntax elements that make up a JavaScript function.

**A good answer covers**
- `function` keyword (or arrow syntax), name
- parameter list in parentheses
- body in curly braces
- `return` statement (optional)

**Common misconceptions**
- the name is required for every function (anonymous functions exist)

**Interviewer follow-ups**
- "Write the same function as a declaration and as an arrow function."

**Practised in:** Hello Functions!

**Verify at:** MDN, "function declaration", "Arrow function expressions"

### PB-FN-03
**Question:** How do you pass arguments to a function? Explain the concept of parameter passing and provide an example.

**A good answer covers**
- parameters in the definition, arguments in the call
- arguments are matched by position
- missing argument → parameter is `undefined`; default parameters
- primitives: the value is copied; objects/arrays: the *reference* is copied, so mutating them inside is visible outside, but reassigning the parameter is not

**Common misconceptions**
- "parameter" and "argument" are the same word

**Interviewer follow-ups**
- "You pass an array to a function that pushes into it. What happens to the original?"

**Practised in:** Hello Functions!, Password validator, Functional calculator, Memorize numbers

**Verify at:** MDN, "Functions" (Guide), "Default parameters"

### PB-FN-04
**Question:** What is the difference between function expressions and function declarations? Provide examples of each.

**A good answer covers**
- declaration: `function name() {}` as a statement
- expression: a function assigned to a variable (`const f = function () {}` or arrow)
- declarations are hoisted (callable before the line); expressions are not
- when to prefer one or the other

**Common misconceptions**
- "arrow functions are the same as declarations"

**Interviewer follow-ups**
- "Can you call a function before the line it is defined on? It depends — on what?"

**Practised in:** Greeting styles

**Verify at:** MDN, "function expression", "Hoisting" (Glossary)

### PB-FN-05
**Question:** Explain what a callback function is in JavaScript.

**A good answer covers**
- a function passed as an argument to another function
- the receiving function decides *when* (and whether) to call it
- functions are values in JS, which is what makes this possible
- at least one concrete example (`forEach` / `map` / `filter`, event listener, `setTimeout`)

**Common misconceptions**
- "Callbacks are always asynchronous" (`map` calls it synchronously)
- writing `fn()` instead of `fn` when passing it

**Interviewer follow-ups**
- "What's the difference between passing `sayHi` and passing `sayHi()`?"
- "Write a function that takes a callback and calls it twice."

**Practised in:** Greeting styles, Functional trio, Expense manager, Secure ERP, Events around us

**Verify at:** MDN Glossary, "Callback function"

### PB-FN-06
**Question:** What is the scope of variables in JavaScript functions? Explain the difference between local and global variables.

**A good answer covers**
- scope = where a variable is visible
- local (function / block) vs. global
- `let` / `const` are block-scoped
- inner functions can see outer variables, not the other way around
- why many globals cause problems

**Common misconceptions**
- a variable declared inside an `if` with `let` is visible after the `if`

**Interviewer follow-ups**
- "Two functions both declare `count`. Do they affect each other?"

**Practised in:** Hangman, Snail mail

**Verify at:** MDN, "Scope" (Glossary)
