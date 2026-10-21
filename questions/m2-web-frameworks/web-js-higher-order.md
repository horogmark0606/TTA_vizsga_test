# web-js-higher-order

Module 2 · Web Frameworks · workbook section "JavaScript Language Features" (WEB-LANG-09 – WEB-LANG-12).
Source: the module's Tech Interview Workbook. Rubrics drafted 2026-10-19; flagged items reviewed by the mentor, full review in progress.
Rubrics are for the agent only: never show them or turn them into a model answer (see AGENTS.md).

### WEB-LANG-09
**Question:** What are higher-order functions in JavaScript?

**A good answer covers**
- a function that takes a function as an argument and / or returns a function
- possible because functions are values
- examples: `map`, `filter`, `addEventListener`, `setTimeout`

**Common misconceptions**
- "a higher-order function is any function inside a function"

**Interviewer follow-ups**
- "Write a function that returns a function."

**Practised in:** My Little Gallery

**Verify at:** MDN Glossary, "First-class function"

### WEB-LANG-10
**Question:** Explain the purpose and functionality of the map function in JavaScript. How does it differ from the filter and reduce functions?

**A good answer covers**
- `map`: same length, each item transformed by the callback
- `filter`: same items, possibly fewer, chosen by a boolean callback
- `reduce`: everything combined into one value, with an accumulator
- all three return something new and don't mutate the original

**Common misconceptions**
- `map` used for side effects only (that's `forEach`)

**Interviewer follow-ups**
- "Get the names of all adults from a list of people. Which methods, in what order?"

**Practised in:** Weather in the Capitals

**Verify at:** MDN, `Array.prototype.map()`

### WEB-LANG-11
**Question:** How can the filter function be used to selectively extract elements from an array based on a given condition? Provide an example where the filter function is used to create a new array with only the elements that meet the specified criteria.

**A good answer covers**
- the callback returns true / false for each item
- the result is a new array with the items where it returned true
- the original array is unchanged
- a concrete example

**Common misconceptions**
- `filter` returns the first match (that's `find`)

**Interviewer follow-ups**
- "What does `filter` return if nothing matches?"

**Practised in:** Fetch the Globe, My Little Gallery, World traveler

**Verify at:** MDN, `Array.prototype.filter()`

### WEB-LANG-12
**Question:** What is the role of the reduce function in JavaScript? How can it be used to aggregate or combine the elements of an array into a single value? Provide an example where the reduce function is used to calculate a cumulative sum or find the maximum value in an array.

**A good answer covers**
- callback `(accumulator, current) => newAccumulator`
- the initial value, and why to provide it
- example: sum, maximum
- the "single value" can be an object or array (grouping)

**Common misconceptions**
- reduce can only produce numbers

**Interviewer follow-ups**
- "What happens with `reduce` on an empty array and no initial value?"

**Practised in:** Your very own TODO list, World traveler

**Verify at:** MDN, `Array.prototype.reduce()`
