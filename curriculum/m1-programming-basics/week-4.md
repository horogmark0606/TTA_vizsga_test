# Programming Basics — Higher-order functions

> Project cards for Week 4 — Higher-order functions. Concept level only: no project descriptions,
> tasks or solutions. Question IDs point to topics in `questions/index.yaml`.
> Status: drafted 2026-10-19; mentor review in progress.

## Week 4 — Higher-order functions

### PB · Greeting styles (solo, week 4)

**Concepts to understand**
- Functions are values: they can be stored and passed around.
- A higher-order function: takes a function as a parameter.
- Anonymous functions and arrow functions.
- Passing a function (`fn`) vs. passing its result (`fn()`).

**Typical pitfalls**
- Calling the function while passing it.

**Explain-your-own-code prompts**
- "What's the difference between passing `shout` and passing `shout('Ann')`?"
- "Rewrite one of your functions as an arrow function. What changed?"

**Related questions:** PB-FN-04, PB-FN-05

### PB · Functional trio (solo, week 4)

**Concepts to understand**
- How `map`, `filter` and `reduce` work inside: a loop that calls the callback for each item.
- What the callback receives and what it must return in each case.
- Returning a new array instead of changing the input.
- The accumulator and its starting value in `reduce`.
- Testing with different callbacks.

**Typical pitfalls**
- Forgetting the starting value of the accumulator.
- Pushing the original item instead of the callback's result (map) or the item itself (filter).

**Explain-your-own-code prompts**
- "Explain your `reduce` with a small array. What is the accumulator after each step?"
- "Who calls the callback: you or your function?"

**Related questions:** PB-FN-05, PB-BUILTIN-02, PB-BUILTIN-05, PB-LANG-02, PB-ALG-06

### PB · Expense manager (solo, week 4)

**Concepts to understand**
- Using the built-in `map`, `filter`, `reduce` on an array of objects.
- Choosing which one fits: transform, select, or combine into one value.
- Template literals to build output strings.
- Writing tests for functions.

**Typical pitfalls**
- Using `map` when nothing should be transformed (or `forEach` when a result is needed).
- `reduce` without a starting value on an empty array.

**Explain-your-own-code prompts**
- "Why is this one a `filter` and not a `map`?"
- "What happens to your total when the list is empty?"

**Related questions:** PB-BUILTIN-02, PB-BUILTIN-05, PB-FN-05

### PB · Secure ERP (team, week 4)

**Concepts to understand**
- Create / read / update / delete on arrays **without** changing the original (immutability).
- Chaining array methods: first select the records, then transform or total them.
- Grouping and aggregating with `reduce` into an object.
- Splitting a program into modules and connecting them with a shared menu.
- Dates as values to compare.

**Typical pitfalls**
- Modifying the object inside the array when "updating" (the original changes too).
- Group-by accumulator not initialised for a new key.

**Explain-your-own-code prompts**
- "How can you show that your update doesn't change the original array?"
- "Walk me through your group-by with three records."
- "How do the modules talk to each other?"

**Related questions:** PB-LANG-01, PB-LANG-02, PB-BUILTIN-02, PB-FN-05, PB-DATA-04
