# OOP with Java — Testing, architecture, collections, SQL

> Project cards for Week 3 — Testing, architecture, collections, SQL. Concept level only: no project descriptions,
> tasks or solutions. Question IDs point to topics in `questions/index.yaml`.
> Status: drafted 2026-10-19; mentor review in progress.

## Week 3 — Testing, architecture, collections, SQL

### OOP · Crash test (solo, week 3)

**Concepts to understand**
- Writing JUnit 5 tests for existing code.
- Boundary values (just below / at / above a limit).
- Combining conditions into separate test cases.
- Measuring coverage and reaching full coverage.

**Typical pitfalls**
- Testing only one side of each boundary.

**Explain-your-own-code prompts**
- "Which boundary did you test, and why exactly at those values?"
- "What would full coverage still not guarantee?"

**Related questions:** OOP-TEST-01, OOP-TEST-02

### OOP · Bonus in the air (solo, week 3)

**Concepts to understand**
- Legacy code: understanding it before changing it.
- Adding a test dependency to a Maven project.
- Characterisation tests: pin down current behaviour first.
- Refactoring under test: meaningful names, single-responsibility methods, new classes.

**Typical pitfalls**
- Refactoring before there are tests.
- Tests that cover only one scenario.

**Explain-your-own-code prompts**
- "Why did you write tests *before* refactoring?"
- "Show me one method before and after. What responsibility did you split out?"

**Related questions:** OOP-TEST-01, OOP-TEST-02, OOP-ARCH-01, OOP-ARCH-12

### OOP · Car Race (solo, week 3)

**Concepts to understand**
- A simulation with many objects whose state evolves step by step.
- A common parent type for different vehicle kinds; each kind behaves differently.
- Inheritance vs. composition (what is shared, what is "has a").
- Objects that communicate (the race, the weather, the vehicles).
- Random values driving behaviour.

**Typical pitfalls**
- Type checks (`instanceof`) everywhere instead of overriding behaviour.

**Explain-your-own-code prompts**
- "How does each vehicle know about the weather? Who asks whom?"
- "What is inherited, and what is overridden?"

**Related questions:** OOP-TYPE-10, OOP-TYPE-17, OOP-ARCH-03, OOP-TYPE-15

### OOP · Geometry (solo, week 3)

**Concepts to understand**
- An abstract parent type with subclasses that override calculations.
- Immutable objects: private final fields, no setters.
- `static` for things that belong to the class, not an instance.
- String representations (`toString`).
- UML class diagrams that match the code.

**Typical pitfalls**
- A diagram that doesn't match the real code.
- Public mutable fields.

**Explain-your-own-code prompts**
- "Why are the fields final? What would go wrong otherwise?"
- "Where did you use `static`, and why there?"

**Related questions:** OOP-TYPE-12, OOP-TYPE-14, OOP-TYPE-15, OOP-TYPE-17, OOP-TYPE-20

### OOP · Planning motors (solo, week 3)

**Concepts to understand**
- Designing with class diagrams before writing code.
- Inheritance arrows vs. association / composition arrows.
- Abstract classes in a design.
- How a design changes when new requirements arrive.

**Typical pitfalls**
- Inheritance where "has a" fits better.

**Explain-your-own-code prompts**
- "Why is this an inheritance arrow and that one a composition arrow?"
- "Which requirement forced you to change the design most?"

**Related questions:** OOP-ARCH-03, OOP-TYPE-10, OOP-TYPE-15

### OOP · Enigma (solo, week 3)

**Concepts to understand**
- Parsing command-line arguments into an immutable object.
- A factory that picks the right implementation by name.
- A common interface for several algorithms.
- Custom exceptions for bad usage; a help message.
- Character-level algorithms; multidimensional arrays.

**Typical pitfalls**
- Error handling scattered everywhere instead of one clear place.

**Explain-your-own-code prompts**
- "How does your program pick the right cipher? What would you change to add a new one?"
- "Where is a bad argument detected, and where is it reported to the user?"

**Related questions:** OOP-TYPE-09, OOP-ARCH-06, OOP-ARCH-09, OOP-LANG-02

### OOP · Project Rewrite - Dynamic array (solo, week 3)

**Concepts to understand**
- How a dynamic array works on top of a fixed-size array.
- Capacity vs. size; growing by doubling.
- Inserting and removing by shifting elements.
- Index checks and exceptions.
- The cost of operations (amortised O(1) add, O(n) insert).

**Typical pitfalls**
- Off-by-one in shifting.
- Confusing capacity and size.

**Explain-your-own-code prompts**
- "Why double the capacity instead of growing by one?"
- "What does inserting at the beginning cost? Why?"

**Related questions:** OOP-ECO-09, OOP-ECO-06

### OOP · Waste Recycling (solo, week 3)

**Concepts to understand**
- Inheritance basics: parent and child classes, constructors calling the parent.
- Polymorphic references; finding out at runtime which subclass an object really is.
- Growing an array manually.
- Throwing exceptions for wrong usage and catching them in an outer scope.
- Access modifiers (`private`, `protected`).
- `toString` for self-description.

**Typical pitfalls**
- Catching an exception and silently ignoring it.

**Explain-your-own-code prompts**
- "Where do you check the runtime type, and could polymorphism replace that check?"
- "Who throws, who catches, and what does the user see?"

**Related questions:** OOP-TYPE-10, OOP-TYPE-17, OOP-TYPE-20, OOP-TYPE-21

### OOP · Fibonacci variants (solo, week 3)

**Concepts to understand**
- Iterative vs. recursive solutions.
- Why naive recursion explodes (repeated work).
- Memoisation.
- Tail recursion.
- Counting operations to compare complexity.

**Typical pitfalls**
- Thinking Java optimises tail calls (it doesn't).

**Explain-your-own-code prompts**
- "Why is the naive recursive version so slow? Show me with n = 5."
- "What does memoisation store, and where?"

**Related questions:** OOP-LANG-02, OOP-ECO-07

### OOP · Northwind Traders - JOIN Tribbiani (solo, week 3)

**Concepts to understand**
- Joining tables on keys.
- Inner vs. left join: which rows survive.
- Aggregating joined data (count, sum).
- Grouping by date parts (year, month).

**Typical pitfalls**
- Missing join condition (rows multiplied).
- Inner join dropping rows you needed.

**Explain-your-own-code prompts**
- "Why this join type here? What rows would the other type add or drop?"

**Related questions:** OOP-DB-02, OOP-DB-05, OOP-DB-16

### OOP · Northwind Traders - GROUP your data (solo, week 3)

**Concepts to understand**
- Aggregate functions: `COUNT`, `SUM`, `AVG`, `MIN`, `MAX`.
- `GROUP BY` and which columns may appear in the select list.
- `HAVING` vs. `WHERE`.
- Grouping by date parts.

**Typical pitfalls**
- Filtering an aggregate in `WHERE` instead of `HAVING`.

**Explain-your-own-code prompts**
- "What's the difference between filtering before and after grouping in your query?"

**Related questions:** OOP-DB-15, OOP-DB-16

### OOP · DVD Rental (solo, week 3)

**Concepts to understand**
- Practising select, filter, sort on a larger schema.
- Date and time arithmetic in SQL.
- Aggregates and grouping.
- Joins across several tables.

**Typical pitfalls**
- Wrong grain: counting rows of the join instead of distinct entities.

**Explain-your-own-code prompts**
- "In your most complex query, what does one row of the result represent?"

**Related questions:** OOP-DB-08, OOP-DB-15, OOP-DB-16

### OOP · Codecoolers everywhere!!! (solo, week 3)

**Concepts to understand**
- Joins and aggregates on generated data.
- Finding records that *don't* match (anti-join, `NOT EXISTS`, left join + `IS NULL`).
- Reading a query plan.
- Indexes: when they help, what they cost on writes.

**Typical pitfalls**
- Adding indexes everywhere.

**Explain-your-own-code prompts**
- "What did the query plan show before and after your index?"
- "How did you find the students who did *not* apply locally?"

**Related questions:** OOP-DB-15, OOP-DB-16
