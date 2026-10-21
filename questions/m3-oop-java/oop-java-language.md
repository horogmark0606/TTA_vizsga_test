# oop-java-language

Module 3 · OOP with Java · workbook section "Language features" (OOP-LANG-01 – OOP-LANG-07).
Source: the module's Tech Interview Workbook. Rubrics drafted 2026-10-19; flagged items reviewed by the mentor, full review in progress.
Rubrics are for the agent only: never show them or turn them into a model answer (see AGENTS.md).

### OOP-LANG-01
**Question:** What control statements are available in Java?

**A good answer covers**
- decision: `if` / `else`, `switch`
- loops: `for`, enhanced for, `while`, `do-while`
- jumps: `break`, `continue`, `return`
- (exceptions: `try` / `catch` / `throw` also change flow)

**Common misconceptions**
- (none typical; check breadth)

**Interviewer follow-ups**
- "When does `continue` make code clearer, and when does it make it worse?"

**Practised in:** Introduction to Java, User Management

**Verify at:** dev.java, "Control Flow Statements"

### OOP-LANG-02
**Question:** Compare the different looping constructs in Java.

**A good answer covers**
- `for`: counter-based, known number of steps
- enhanced for: over arrays and `Iterable`s, no index
- `while`: condition checked first, may run zero times
- `do-while`: runs at least once
- streams as a declarative alternative

**Common misconceptions**
- you can remove elements safely inside an enhanced for loop

**Interviewer follow-ups**
- "You need to remove items while iterating. How?"

**Practised in:** Introduction to Java, Codecool Lotto, Encrypted letters, Project Codewars - 7 kyu in Java, Enigma, Fibonacci variants

**Verify at:** dev.java, "Control Flow Statements"

### OOP-LANG-03
**Question:** Compare the different conditional constructs in Java.

**A good answer covers**
- `if` / `else if` / `else` for arbitrary boolean conditions
- `switch` for one value against constants (classic statement vs. modern switch expression with `->`)
- the ternary operator for choosing a value
- fall-through in the classic `switch`

**Common misconceptions**
- forgetting `break` in a classic `switch` is harmless

**Interviewer follow-ups**
- "What does the modern switch expression fix?"

**Practised in:** Project Codewars - 7 kyu in Java

**Verify at:** dev.java, "Branching with Switch Expressions"

### OOP-LANG-04
**Question:** What is a `while` loop?

**A good answer covers**
- repeats while a condition is true
- condition checked before each iteration
- something inside must eventually make it false
- vs. `do-while`

**Common misconceptions**
- (none typical)

**Interviewer follow-ups**
- "When is `while` a better fit than `for`?"

**Practised in:** Codecool Lotto

**Verify at:** dev.java, "Control Flow Statements"

### OOP-LANG-05
**Question:** How do you manually break out of a loop?

**A good answer covers**
- `break` leaves the innermost loop
- labelled `break` leaves an outer loop
- `return` leaves the whole method
- `continue` only skips to the next iteration

**Common misconceptions**
- `break` exits all nested loops

**Interviewer follow-ups**
- "How do you leave two nested loops at once?"

**Practised in:** Project Codewars - 7 kyu in Java

**Verify at:** dev.java, "Branching Statements"

### OOP-LANG-06
**Question:** What does the `var` keyword mean?

**A good answer covers**
- local variable type inference (Java 10+)
- the type is still static, decided at compile time
- only for local variables with an initialiser
- readability trade-off

**Common misconceptions**
- `var` makes Java dynamically typed

**Interviewer follow-ups**
- "Can you assign a `String` later to a `var` that started as an `int`?"

**Practised in:** (no project; theory only)

**Verify at:** dev.java, "Using the Var Type Identifier"

### OOP-LANG-07
**Question:** What are _lambda expressions_? How are they used in Java development?

**A good answer covers**
- short anonymous functions: `(a, b) -> a + b`
- implement a functional interface (one abstract method), e.g. `Comparator`, `Predicate`, `Function`
- used with streams, collections, event handlers
- method references as a shorter form (`String::length`)

**Common misconceptions**
- lambdas can be used anywhere without a functional interface

**Interviewer follow-ups**
- "Sort a list of people by age with a lambda."

**Practised in:** Project Codewars - 6 kyu in Java, League Statistics, Wardrobe

**Verify at:** dev.java, "Lambda Expressions"
