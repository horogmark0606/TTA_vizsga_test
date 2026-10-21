# pb-builtins

Module 1 · Programming Basics · workbook section "Built-in Features" (PB-BUILTIN-01 – PB-BUILTIN-05).
Source: the module's Tech Interview Workbook. Rubrics drafted 2026-10-19; flagged items reviewed by the mentor, full review in progress.
Rubrics are for the agent only: never show them or turn them into a model answer (see AGENTS.md).

### PB-BUILTIN-01
**Question:** What are some commonly used built-in functions or methods in JavaScript for working with strings? Provide examples and explain their usage.

**A good answer covers**
- at least 4–5 methods with purpose (e.g. `toLowerCase`, `includes`, `indexOf`, `slice`, `split`, `trim`, `replace`, `startsWith`)
- string methods return a new string; the original never changes
- an example from their own code

**Common misconceptions**
- `str.toUpperCase()` changes `str`

**Interviewer follow-ups**
- "How would you check whether a word is a palindrome?"

**Practised in:** Become a coder, Phonebook, Password validator, Snail mail, Wordchain (console), String theory

**Verify at:** MDN, "String"

### PB-BUILTIN-02
**Question:** Name at least five built-in functions or methods in JavaScript for manipulating arrays. Describe how each function/method works and provide an example for each.

**A good answer covers**
- at least five, with purpose (e.g. `push`, `pop`, `slice`, `splice`, `indexOf`, `includes`, `map`, `filter`, `reduce`, `find`, `sort`)
- which ones change the array (`push`, `pop`, `splice`, `sort`) and which return something new (`slice`, `map`, `filter`)
- an example for each

**Common misconceptions**
- `slice` and `splice` do the same thing
- `map` changes the original array

**Interviewer follow-ups**
- "Which of these change the original array?"

**Practised in:** Basics of arrays, Typewriter backspaces, Vacation expenses, String theory, Functional trio, Expense manager, Secure ERP, More on product list, Movie DB site, More on favorite products, Neighbouring countries

**Verify at:** MDN, "Array"

### PB-BUILTIN-03
**Question:** How can you use built-in functions or methods in JavaScript to perform mathematical operations? Give examples of commonly used functions or methods for mathematical calculations.

**A good answer covers**
- the `Math` object
- e.g. `Math.round`, `floor`, `ceil`, `max`, `min`, `abs`, `pow`, `sqrt`
- `Math.random()` and how to get a random integer in a range

**Common misconceptions**
- `Math.random()` can return 1

**Interviewer follow-ups**
- "Give me a random index for an array of length 5."

**Practised in:** Hangman, Billionaire game, Memorize numbers, Battleship.js (console)

**Verify at:** MDN, "Math"

### PB-BUILTIN-04
**Question:** What are some built-in functions or methods in JavaScript for manipulating numbers? Describe their functionality and give examples of how they can be used.

**A good answer covers**
- converting: `Number()`, `parseInt`, `parseFloat`
- checking: `Number.isNaN`, `Number.isInteger`
- formatting: `toFixed`
- difference between `Number('12px')` and `parseInt('12px')`

**Common misconceptions**
- `toFixed` returns a number (it returns a string)

**Interviewer follow-ups**
- "How do you check that user input is a valid whole number?"

**Practised in:** Calculator, Functional calculator, More on product list

**Verify at:** MDN, "Number"

### PB-BUILTIN-05
**Question:** Discuss the differences between `for` loops and the `forEach` method in JavaScript.

**A good answer covers**
- `forEach` is an array method that takes a callback
- `for` gives control over start, step, and stopping early
- `break` / early `return` don't stop `forEach`
- readability trade-off

**Common misconceptions**
- `forEach` returns a new array

**Interviewer follow-ups**
- "You want to stop at the first negative number. Which do you use?"

**Practised in:** Functional trio, Expense manager

**Verify at:** MDN, `Array.prototype.forEach()`
