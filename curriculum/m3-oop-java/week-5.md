# OOP with Java — Advanced OOP, collections, streams, mocking, Spring

> Project cards for Week 5 — Advanced OOP, collections, streams, mocking, Spring. Concept level only: no project descriptions,
> tasks or solutions. Question IDs point to topics in `questions/index.yaml`.
> Status: drafted 2026-10-19; mentor review in progress.

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
