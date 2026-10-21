# OOP with Java — project cards

> Module 3 of the FullStack course: Java, OOP and design principles, unit
> testing with JUnit and Mockito, SQL with PostgreSQL and JDBC, collections,
> streams, Spring Boot. Question IDs (`OOP-…`) refer to `OOP-questions.md`.
>
> Status: **draft, mentor review pending.**

---

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

---

## Week 2 — Structure and principles

### OOP · Fly that drone (solo, week 2)

**Concepts to understand**
- The Open/Closed Principle: adding new behaviour without changing existing code.
- Polymorphism: each kind of movement as its own class behind a common interface.
- Single responsibility per class.
- Parameterised unit tests: one test, many cases.

**Typical pitfalls**
- A growing `switch` that has to be edited for every new movement.

**Explain-your-own-code prompts**
- "Add a new kind of movement. Which files do you touch, and which don't you touch?"
- "How does your parameterised test get its cases?"

**Related questions:** OOP-ARCH-06, OOP-ARCH-01, OOP-TYPE-09, OOP-TEST-03

### OOP · Mighty text adventure (team, week 2)

**Concepts to understand**
- Data classes vs. service / logic classes.
- MVC: keeping display separate from game logic.
- Modelling a game world: areas, connections, actions, the player.
- Single Responsibility Principle.
- Input handling: case-insensitive commands, short and long forms, help.
- Win / lose checks every turn.

**Typical pitfalls**
- Printing from inside the logic classes.
- One huge class that does everything.

**Explain-your-own-code prompts**
- "Which classes would change if you replaced the console with a web UI?"
- "How does an action lead the player into another area? Show me in your data."

**Related questions:** OOP-ARCH-01, OOP-ARCH-04, OOP-ARCH-05, OOP-TYPE-06

### OOP · Project Codewars - 7 kyu in Java (solo, week 2)

**Concepts to understand**
- Short algorithmic exercises: strings, arrays, loops, conditionals, methods.
- Reading a problem statement precisely, including edge cases.
- Working against hidden tests.
- Learning from other people's solutions after solving.

**Typical pitfalls**
- Solving only the visible examples.

**Explain-your-own-code prompts**
- "Pick one kata. Walk me through your solution, then through a better one you saw afterwards."

**Related questions:** OOP-LANG-02, OOP-LANG-03, OOP-LANG-05, OOP-TYPE-23

---

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

---

## Week 4 — Teamwork

### OOP · Secure ERP (team, week 4)

**Concepts to understand**
- Modular design: one module per business area.
- MVC: separate the menu / view, the controllers and the data layer.
- CRUD operations, plus search, filter and aggregation over records.
- Clean code and following requirements exactly.
- Team collaboration on one codebase.

**Typical pitfalls**
- Modules that depend on each other's internals.
- Duplicated code across modules.

**Explain-your-own-code prompts**
- "Which layer would change if the data moved from files to a database?"
- "What's shared between the modules, and how?"

**Related questions:** OOP-ARCH-01, OOP-ARCH-04, OOP-ARCH-05, OOP-ARCH-15

### OOP · Project Codewars - 6 kyu in Java (team, week 4)

**Concepts to understand**
- Harder algorithmic exercises: more edge cases, more efficient solutions.
- Choosing the right collection for the problem.
- Streams and lambdas as an alternative to loops.

**Typical pitfalls**
- Brute force that times out.

**Explain-your-own-code prompts**
- "Show me a kata where your first solution was too slow. What did you change?"

**Related questions:** OOP-LANG-07, OOP-ECO-08, OOP-ECO-07

---

## Week 5 — Advanced OOP, collections, streams, mocking, Spring

### OOP · Starfleet Control (solo, week 5)

**Concepts to understand**
- Object-oriented design from written rules.
- A hierarchy of types with shared and specialised behaviour.
- Immutability after construction.
- Objects cooperating (docking, logs, a control centre that lists everything).

**Typical pitfalls**
- Rules duplicated in several subclasses instead of in the parent.

**Explain-your-own-code prompts**
- "Which rules live in the parent and which in the children? Why?"
- "How do the objects find each other?"

**Related questions:** OOP-TYPE-10, OOP-TYPE-15, OOP-ARCH-03, OOP-ARCH-07

### OOP · Life of the Ants (solo, week 5)

**Concepts to understand**
- Designing with a class diagram first; updating it to match the result.
- A common abstract type with a different `act` behaviour per kind.
- A simulation loop: update every object, then display.
- Movement rules and positions on a grid.

**Typical pitfalls**
- A loop full of type checks instead of overridden methods.

**Explain-your-own-code prompts**
- "How does the colony update all the different kinds without knowing which is which?"
- "How much did your final diagram differ from the first plan? Why?"

**Related questions:** OOP-TYPE-15, OOP-TYPE-17, OOP-ARCH-07, OOP-ARCH-03

### OOP · Collections in Java (solo, week 5)

**Concepts to understand**
- The main collection interfaces, how they relate, and where `Map` fits in.
- Implementations and their trade-offs.
- Replacing fixed arrays with collections in an existing project.

**Typical pitfalls**
- Declaring variables by implementation type instead of interface type.

**Explain-your-own-code prompts**
- "For each array you replaced: which collection did you pick, and why?"

**Related questions:** OOP-ECO-05, OOP-ECO-06, OOP-ECO-07, OOP-ECO-08, OOP-ECO-10

### OOP · Project Rewrite - Linked list (solo, week 5)

**Concepts to understand**
- How a linked list works: nodes and references.
- Generics: one implementation for any element type.
- Add, insert, get, index-of, size by walking the list.
- Cost of operations compared with a dynamic array.

**Typical pitfalls**
- Losing the rest of the list when re-linking nodes.
- Not handling the empty list and the head separately.

**Explain-your-own-code prompts**
- "Walk me through inserting in the middle: which references change, in what order?"
- "Why is `get(i)` slow here and fast in an array list?"

**Related questions:** OOP-ECO-09, OOP-TYPE-02, OOP-TYPE-22

### OOP · The History (solo, week 5)

**Concepts to understand**
- Coding against an interface with two implementations.
- Correctness tests vs. performance tests.
- Array list vs. linked list in real measurements.
- Iterators: how they work, and removing safely while iterating.
- Documenting an interface (Javadoc).

**Typical pitfalls**
- Modifying a list inside a for-each loop.

**Explain-your-own-code prompts**
- "Which implementation won which performance test, and why?"
- "How did you remove elements while iterating?"

**Related questions:** OOP-ECO-05, OOP-ECO-09, OOP-TYPE-09

### OOP · League Statistics (solo, week 5)

**Concepts to understand**
- The Stream API: map, filter, sorted, collect, grouping.
- Lambdas and method references.
- Statistics without explicit loops.
- MVC: logic separate from display.
- Subclasses with different behaviour (player roles).

**Typical pitfalls**
- Unreadable one-line streams.

**Explain-your-own-code prompts**
- "Read one of your stream pipelines step by step. What is in the stream after each step?"
- "When would a plain loop be clearer?"

**Related questions:** OOP-LANG-07, OOP-ARCH-04, OOP-TYPE-17

### OOP · Wardrobe (solo, week 5)

**Concepts to understand**
- Objects with a unique ID and fields set only at creation.
- Generics.
- `Optional` instead of returning `null`.
- Built-in exceptions for invalid operations.
- Capacity rules enforced by the objects themselves.

**Typical pitfalls**
- `Optional.get()` without checking.

**Explain-your-own-code prompts**
- "Why return an `Optional` here instead of `null`?"
- "Which object is responsible for refusing an invalid action?"

**Related questions:** OOP-TYPE-19, OOP-TYPE-14, OOP-TYPE-26, OOP-LANG-07

### OOP · Phone book (solo, week 5)

**Concepts to understand**
- A service class that depends on a data-access interface.
- Test doubles: stub, fake, mock.
- Mockito: creating mocks, stubbing return values, verifying calls.
- Testing service logic without a real database.

**Typical pitfalls**
- Calling a fake a "mock" (and the other way round).

**Explain-your-own-code prompts**
- "What's the difference between your stub, your fake and your Mockito mock?"
- "Why does the service depend on an interface, not a concrete class?"

**Related questions:** OOP-TEST-05, OOP-TEST-06, OOP-ARCH-08

### OOP · StockTrader (solo, week 5)

**Concepts to understand**
- Dependency injection: pass dependencies in instead of creating them inside.
- Removing hidden dependencies and singletons.
- Loose coupling: a new logger type without changing existing code.
- Mocking external services (remote reads).
- Test reports.

**Typical pitfalls**
- `new` inside the class that should receive the dependency.

**Explain-your-own-code prompts**
- "Before your change, why was this class hard to test?"
- "How do you test the case where the remote service fails?"

**Related questions:** OOP-ARCH-08, OOP-ARCH-06, OOP-TEST-05, OOP-TEST-06

### OOP · Histogram (solo, week 5)

**Concepts to understand**
- Unit tests for boundary conditions and exceptions.
- Test resources (input files) for edge cases.
- Setup and teardown annotations.
- Normalising values.
- Making tests fast and free of duplication; full coverage.

**Typical pitfalls**
- Copy-pasted test bodies.

**Explain-your-own-code prompts**
- "Which edge cases do your test files cover?"
- "What runs before each test and what runs once? Why?"

**Related questions:** OOP-TEST-01, OOP-TEST-02, OOP-TEST-03

### OOP · Bookshelf API (solo, week 5)

**Concepts to understand**
- A Spring Boot project and its dependencies.
- Layers: controller → service → DAO → database.
- Model classes.
- REST endpoints for CRUD with the right HTTP methods and path variables.
- Constructor injection.
- Testing endpoints with Swagger.

**Typical pitfalls**
- Business logic inside the controller.

**Explain-your-own-code prompts**
- "A request to get one book arrives. Which layers does it pass through, and what does each do?"
- "Who creates your service object, and how does the controller get it?"

**Related questions:** OOP-ARCH-04, OOP-ARCH-05, OOP-ARCH-08, OOP-ARCH-15, OOP-DB-11

---

## Week 6 — Teamwork

### OOP · AskMate OOP (team, week 6)

**Concepts to understand**
- A Spring Boot web application with a separate frontend.
- The Repository Pattern for data access.
- REST endpoints for questions, answers, users; path variables.
- Registration, login, logout.
- A service layer covered by unit tests.
- Search and aggregations (points, most active users).

**Typical pitfalls**
- SQL scattered through controllers.
- Passwords stored in plain text.

**Explain-your-own-code prompts**
- "Trace 'post an answer' from the button to the database row."
- "What does your repository hide from the service?"
- "How is a user's login remembered between requests?"

**Related questions:** OOP-ARCH-14, OOP-ARCH-15, OOP-ARCH-04, OOP-DB-02, OOP-TEST-01

---

## Weeks 1–6 — Ongoing practice

### OOP · Mockulator (solo, weeks 1–6, ongoing)

**Concepts to understand**
- An interface with several implementations (operations).
- A class that works with any implementation (polymorphism).
- Manual test doubles: writing your own fake implementation for a test.
- Testing error paths with a double that always fails.

**Typical pitfalls**
- Test doubles that contain real logic.

**Explain-your-own-code prompts**
- "Why does your calculator not need to know which operation it gets?"
- "What does your always-failing double let you test?"

**Related questions:** OOP-TYPE-09, OOP-TEST-05, OOP-TEST-06

### OOP · Magic 8 Ball (solo, weeks 1–6, ongoing)

**Concepts to understand**
- Reading resources from the classpath.
- Separating user input, answer choice and the game loop into classes.
- Mockito for testing input and random choice.
- Making randomness testable.

**Typical pitfalls**
- Randomness created inside the class, so tests can't control it.

**Explain-your-own-code prompts**
- "How do you test something that's random?"

**Related questions:** OOP-TEST-05, OOP-ARCH-08, OOP-ARCH-01
