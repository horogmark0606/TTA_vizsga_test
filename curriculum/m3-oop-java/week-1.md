# OOP with Java — Java, classes, testing, SQL basics

> Project cards for Week 1 — Java, classes, testing, SQL basics. Concept level only: no project descriptions,
> tasks or solutions. Question IDs point to topics in `questions/index.yaml`.
> Status: drafted 2026-10-19; mentor review in progress.

## Week 1 — Java, classes, testing, SQL basics

### OOP · What is OOP? (solo, week 1)

**Concepts to understand**
- The big picture: modelling a program as objects that hold state and behaviour.
- The four principles: encapsulation, abstraction, inheritance, polymorphism.
- Static vs. dynamic typing, and what changes coming from JavaScript.

**Typical pitfalls**
- Listing the four principles without being able to give an example of each.

**Explain-your-own-code prompts**
- "Pick one of your Java classes. Which of the four principles does it use, and where?"
- "What did static typing catch for you that JavaScript wouldn't have?"

**Related questions:** OOP-TYPE-03, OOP-TYPE-04, OOP-TYPE-10, OOP-ECO-01

### OOP · Introduction to Java (solo, week 1)

**Concepts to understand**
- Basic Java syntax: variables with types, conditionals, loops.
- Arrays vs. `ArrayList`.
- String methods.
- First look at classes and objects.

**Typical pitfalls**
- Comparing strings with `==`.

**Explain-your-own-code prompts**
- "What's the difference between an array and an `ArrayList`? When did you need which?"

**Related questions:** OOP-LANG-01, OOP-LANG-02, OOP-TYPE-01, OOP-TYPE-23, OOP-ECO-09

### OOP · Java basics (solo, week 1)

**Concepts to understand**
- The structure of a Java program: package, class, `main`.
- Compile, then run: source → bytecode → JVM.
- Methods: parameters, return types, `static`.
- The type system: primitives vs. reference types, wrapper classes.
- Parsing strings into numbers.

**Typical pitfalls**
- Thinking Java runs the source file directly.
- Mixing up `int` and `Integer` (and `null`).

**Explain-your-own-code prompts**
- "What happens between writing a `.java` file and seeing output?"
- "Why is `main` static?"

**Related questions:** OOP-ECO-01, OOP-ECO-02, OOP-ECO-03, OOP-ECO-04, OOP-TYPE-01, OOP-TYPE-02, OOP-TYPE-12, OOP-TYPE-13

### OOP · User Management (solo, week 1)

**Concepts to understand**
- Implementing methods from a given signature.
- Console input and output in Java.
- Parsing strings to numbers and handling bad input.
- Arrays of primitives and of strings.
- Overloaded methods (same name, different parameters).

**Typical pitfalls**
- A parsing exception crashes the program.
- Reading a number and then a line (the leftover newline).

**Explain-your-own-code prompts**
- "You have two methods with the same name. How does Java decide which one to call?"
- "What happens when the user types letters where you expect a number?"

**Related questions:** OOP-TYPE-01, OOP-TYPE-16, OOP-TYPE-18, OOP-LANG-01

### OOP · Codecool Lotto (solo, week 1)

**Concepts to understand**
- Splitting a program into input, logic and output methods.
- Random numbers in Java.
- Drawing unique numbers (no repeats).
- Comparing two sets of numbers.
- Letting the computer play: reusing the same logic with a different input source.

**Typical pitfalls**
- Duplicates in the random draw.
- Logic and printing mixed in the same method.

**Explain-your-own-code prompts**
- "How do you guarantee the drawn numbers are unique?"
- "What did you have to change to let the computer play? What could stay the same?"

**Related questions:** OOP-LANG-02, OOP-LANG-04, OOP-ECO-08, OOP-ARCH-01

### OOP · Diligent Deliveries (solo, week 1)

**Concepts to understand**
- Classes with state (fields) and behaviour (methods).
- Constructors that set the initial state.
- Objects that hold other objects (composition).
- A simulation running over several days; state that resets or persists between days.
- Producing a report object from the simulation.

**Typical pitfalls**
- Public fields changed from everywhere.
- State that should reset each day leaks into the next.

**Explain-your-own-code prompts**
- "Which object knows what? Draw the relationships between your classes."
- "What is reset at the start of a day, and where in your code does that happen?"

**Related questions:** OOP-TYPE-03, OOP-TYPE-04, OOP-TYPE-05, OOP-ARCH-03, OOP-ARCH-04

### OOP · Math formulas (solo, week 1)

**Concepts to understand**
- Running unit tests and reading their results.
- Implementing methods until the tests pass.
- Integer arithmetic: remainder, divisibility, greatest common divisor, least common multiple.
- Integer vs. floating-point division; percentages.

**Typical pitfalls**
- Integer division truncates silently.
- Changing the test instead of the code.

**Explain-your-own-code prompts**
- "Read me one test name. What exactly does it check?"
- "Where would integer division have given you the wrong result?"

**Related questions:** OOP-TEST-01, OOP-TEST-02, OOP-TYPE-01

### OOP · Encrypted letters (solo, week 1)

**Concepts to understand**
- Character arithmetic: letters as numbers, wrapping around the alphabet.
- Keeping case and non-letter characters as they are.
- Two ciphers where one is a special case of the other.
- Driving the implementation by existing tests.

**Typical pitfalls**
- Negative remainders when shifting backwards.
- Wrapping that works for lower case but not upper case.

**Explain-your-own-code prompts**
- "How does a letter at the end of the alphabet wrap around in your code?"
- "Why can one cipher reproduce the other?"

**Related questions:** OOP-TEST-01, OOP-TYPE-01, OOP-LANG-02

### OOP · Introduction to SQL (solo, week 1)

**Concepts to understand**
- `SELECT` with chosen columns.
- Filtering with `WHERE`: comparison, `AND` / `OR`, `IN`, `LIKE`, `BETWEEN`.
- Sorting with `ORDER BY`, limiting rows.
- `DISTINCT`.

**Typical pitfalls**
- `= NULL` instead of `IS NULL`.

**Explain-your-own-code prompts**
- "Read one of your queries aloud in plain English."

**Related questions:** OOP-DB-03, OOP-DB-06, OOP-DB-15

### OOP · Northwind Traders – Natural SELECTion (solo, week 1)

**Concepts to understand**
- Reading an unfamiliar schema to find the right table and columns.
- Filtering by dates and date ranges.
- Pattern matching on text.
- Handling missing values (`NULL`).
- Sorting and selecting distinct values.

**Typical pitfalls**
- Date ranges that miss the last day.
- Case-sensitive pattern matches.

**Explain-your-own-code prompts**
- "How did you find which table holds the data you needed?"
- "How does your date filter treat the boundary days?"

**Related questions:** OOP-DB-03, OOP-DB-08, OOP-DB-15

### OOP · Book DB (solo, week 1)

**Concepts to understand**
- Creating tables and sample data for two related entities.
- Connecting to a database from Java with JDBC.
- DAOs: one class per entity that hides the SQL.
- `PreparedStatement` and why it prevents SQL injection.
- Exception handling: wrapping checked exceptions.
- A console UI on top of the DAOs.

**Typical pitfalls**
- Building SQL by string concatenation.
- Connections that are never closed.

**Explain-your-own-code prompts**
- "Why do you use a prepared statement instead of building the SQL string yourself?"
- "Where is your connection opened and where is it closed?"
- "If you switched databases, which classes would have to change?"

**Related questions:** OOP-DB-01, OOP-DB-04, OOP-DB-05, OOP-DB-09, OOP-DB-10, OOP-DB-11, OOP-DB-12, OOP-DB-13, OOP-DB-14, OOP-ARCH-14, OOP-ARCH-15
