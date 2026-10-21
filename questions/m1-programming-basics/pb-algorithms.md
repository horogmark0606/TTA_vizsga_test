# pb-algorithms

Module 1 · Programming Basics · workbook section "Algorithm Basics" (PB-ALG-01 – PB-ALG-06).
Source: the module's Tech Interview Workbook. Rubrics drafted 2026-10-19; flagged items reviewed by the mentor, full review in progress.
Rubrics are for the agent only: never show them or turn them into a model answer (see AGENTS.md).

### PB-ALG-01
**Question:** Provide examples of assignment operators in JavaScript.

**A good answer covers**
- `=`
- compound: `+=`, `-=`, `*=`, `/=`, `%=`
- increment / decrement `++`, `--` (closely related)
- assignment is not comparison

**Common misconceptions**
- confusing `=` with `==` / `===`

**Interviewer follow-ups**
- "What does `x += 1` do when `x` is a string?"

**Practised in:** Calculator

**Verify at:** MDN, "Assignment operators"

### PB-ALG-02
**Question:** Name some of the arithmetic operators in JavaScript.

**A good answer covers**
- `+ - * /`
- `%` (remainder) and a use case (even/odd)
- `**` (exponent)
- `+` also concatenates strings

**Common misconceptions**
- `%` is "percent"

**Interviewer follow-ups**
- "What is `'5' + 3`? And `'5' - 3`? Why?"

**Practised in:** Calculator

**Verify at:** MDN, "Arithmetic operators"

### PB-ALG-03
**Question:** What are the different comparison operators in JavaScript?

**A good answer covers**
- `===` / `!==` strict (no type conversion)
- `==` / `!=` loose (type conversion), and why `===` is preferred
- `<`, `>`, `<=`, `>=`
- comparison returns a boolean

**Common misconceptions**
- `==` and `===` are the same
- objects/arrays are compared by content (they are compared by reference)

**Interviewer follow-ups**
- "What is `0 == ''`? And `0 === ''`?"

**Practised in:** Calculator, Phonebook

**Verify at:** MDN, "Equality comparisons and sameness"

### PB-ALG-04
**Question:** Name a few logical operators used in JavaScript.

**A good answer covers**
- `&&`, `||`, `!`
- what each returns / when it is true
- short-circuiting (the right side may not run)
- bonus: `??`

**Common misconceptions**
- `&&` / `||` always return a boolean (they return one of the operands)

**Interviewer follow-ups**
- "How would you check that a number is between 1 and 9?"

**Practised in:** Phonebook, Snail mail, Billionaire game, Wordchain (console)

**Verify at:** MDN, "Logical AND (&&)", "Logical OR (||)"

### PB-ALG-05
**Question:** Explain the differences between a `for` loop, `for of` loop, and `for in` loop in JavaScript.

**A good answer covers**
- classic `for`: explicit counter, start / condition / step; full control (skip, go backwards, use the index)
- `for...of`: iterates over the *values* of an iterable (array, string)
- `for...in`: iterates over the *keys* (property names) of an object
- `for...in` on an array gives index strings, so it isn't the usual choice for arrays
- when to choose which one

**Common misconceptions**
- "`for...in` and `for...of` are the same thing"
- "`for...of` works on plain objects"

**Interviewer follow-ups**
- "You need both the index and the value. Which loop, and how?"
- "How would you loop over an object's values?"

**Practised in:** Become a coder, Typewriter backspaces, Hangman, Student catalog, Tic-tac-toe-console

**Verify at:** MDN, `for...of`, `for...in`

### PB-ALG-06
**Question:** If you can't use any built-in functions or methods, how would you calculate the average of values in an array?

**A good answer covers**
- a running sum in a loop
- divide by the number of items
- handles the empty array (division by zero → `NaN`)
- can explain it step by step on a small example

**Common misconceptions**
- starting the sum from `undefined` instead of `0`

**Interviewer follow-ups**
- "What does your code return for `[]`? What should it return?"

**Practised in:** Functional trio

**Verify at:** (no single source; check by running it)
