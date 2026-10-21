# pb-data

Module 1 · Programming Basics · workbook section "Data Basics" (PB-DATA-01 – PB-DATA-06).
Source: the module's Tech Interview Workbook. Rubrics drafted 2026-10-19; flagged items reviewed by the mentor, full review in progress.
Rubrics are for the agent only: never show them or turn them into a model answer (see AGENTS.md).

### PB-DATA-01
**Question:** What are the differences between objects, arrays, and primitives in JavaScript? How are they used in programming?

**A good answer covers**
- primitives: a single, simple value (number, string, boolean, …)
- arrays: an ordered list, accessed by numeric index
- objects: a collection of named properties (key → value)
- arrays and objects are reference types and can hold other values (even each other)
- an example of a typical use for each

**Common misconceptions**
- "Arrays are not objects" (they are a special kind of object)

**Interviewer follow-ups**
- "How would you store a list of students, each with a name and age?"

**Practised in:** Basics of arrays

**Verify at:** MDN, "JavaScript data types and data structures"

### PB-DATA-02
**Question:** How would you access the value of a specific key in an object?

**A good answer covers**
- dot notation: `obj.key`
- bracket notation: `obj["key"]`
- bracket notation is needed when the key is in a variable or isn't a valid identifier
- accessing a missing key gives `undefined`, not an error

**Common misconceptions**
- `obj.keyName` works when `keyName` is a variable holding the key

**Interviewer follow-ups**
- "The key name comes from user input. How do you read it?"

**Practised in:** Student catalog

**Verify at:** MDN, "Property accessors"

### PB-DATA-03
**Question:** Explain the concept of key-value pairs in objects and how they differ from indexed elements in arrays.

**A good answer covers**
- object: each value is reached by a meaningful name (key)
- array: each value is reached by its position (index from 0)
- array order matters and is used; object keys describe meaning
- choosing between them depends on whether you look things up by name or by position

**Common misconceptions**
- "Object keys can be any type" (they are strings or symbols)

**Interviewer follow-ups**
- "How would you count how many times each word appears in a text? Which structure?"

**Practised in:** Phonebook, Student catalog, Take me to a nice place, Billionaire game, String theory, Boring buses, Product list, Neighbouring countries

**Verify at:** MDN, "Working with objects", "Indexed collections"

### PB-DATA-04
**Question:** Describe a scenario where you would choose to use an object instead of an array, or vice versa, and explain your reasoning.

**A good answer covers**
- a concrete scenario for an object (one thing with named properties, or lookup by key)
- a concrete scenario for an array (many similar items, order, iteration)
- the reasoning, not just the choice
- bonus: array of objects as a combination

**Common misconceptions**
- picking based on habit with no reasoning

**Interviewer follow-ups**
- "Which did you use in one of your projects, and would you choose differently now?"

**Practised in:** Student catalog, Take me to a nice place, Billionaire game, Secure ERP, Movie DB site

**Verify at:** MDN, "Working with objects"

### PB-DATA-05
**Question:** How can you retrieve the first and last items of an array?

**A good answer covers**
- first: index `0`
- last: index `length - 1`
- (modern) `at(-1)`
- `pop()` / `shift()` also return them **but remove them** from the array

**Common misconceptions**
- `arr[arr.length]` is the last item

**Interviewer follow-ups**
- "What do you get for an empty array?"

**Practised in:** Basics of arrays, Hangman, Wordchain (console)

**Verify at:** MDN, `Array.prototype.at()`, `length`

### PB-DATA-06
**Question:** Identify the five most commonly used primitive types in JavaScript, and provide examples demonstrating when and how to use them?

**A good answer covers**
- number, string, boolean, undefined, null (also: bigint, symbol exist)
- an example use case for each
- `typeof` to check the type

**Common misconceptions**
- "Arrays / objects are primitives"
- "`typeof null` is `'null'`" (it is `'object'`, a historical quirk)

**Interviewer follow-ups**
- "What's the difference between `undefined` and `null` in practice?"

**Practised in:** Calculator, Text Adventure

**Verify at:** MDN, "Primitive" (Glossary), `typeof`
