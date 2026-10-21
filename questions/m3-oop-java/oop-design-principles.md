# oop-design-principles

Module 3 · OOP with Java · workbook section "Architecture" (OOP-ARCH-01 – OOP-ARCH-08).
Source: the module's Tech Interview Workbook. Rubrics drafted 2026-10-19; flagged items reviewed by the mentor, full review in progress.
Rubrics are for the agent only: never show them or turn them into a model answer (see AGENTS.md).

### OOP-ARCH-01
**Question:** Explain the Single Responsibility Principle.

**A good answer covers**
- a class (or method) should have one reason to change
- one job / one concern
- smaller, easier to test and change
- concrete example of splitting a class

**Common misconceptions**
- "a class should have only one method"

**Interviewer follow-ups**
- "Show me a class you split. What were the two responsibilities?"

**Practised in:** Codecool Lotto, Fly that drone, Mighty text adventure, Bonus in the air, Secure ERP, Magic 8 Ball

**Verify at:** Robert C. Martin, "The Single Responsibility Principle" (blog.cleancoder.com)

### OOP-ARCH-02
**Question:** Explain the Interface Segregation Principle.

**A good answer covers**
- clients shouldn't depend on methods they don't use
- prefer several small, focused interfaces over one fat one
- avoids empty / throwing implementations

**Common misconceptions**
- "one interface per class"

**Interviewer follow-ups**
- "What's a sign that an interface is too big?"

**Practised in:** (no project; theory only)

**Verify at:** Robert C. Martin, "Design Principles and Design Patterns"

### OOP-ARCH-03
**Question:** What is _composition over inheritance_?

**A good answer covers**
- build behaviour by holding other objects ("has-a") rather than extending ("is-a")
- more flexible: swap parts at runtime, fewer fragile hierarchies
- inheritance still fits real "is-a" with shared behaviour
- example

**Common misconceptions**
- "never use inheritance"

**Interviewer follow-ups**
- "In your car designs, where was 'has-a' better than 'is-a'?"

**Practised in:** Diligent Deliveries, Car Race, Planning motors, Starfleet Control, Life of the Ants

**Verify at:** *Design Patterns* (GoF), ch. 1; Effective Java, item "Favor composition over inheritance"

### OOP-ARCH-04
**Question:** What is a model class?

**A good answer covers**
- represents domain data (an entity): fields, constructors, accessors
- little or no business logic
- used across layers (often a record or simple class)

**Common misconceptions**
- model = the database table itself

**Interviewer follow-ups**
- "Should a model class print itself to the console?"

**Practised in:** Diligent Deliveries, Mighty text adventure, Secure ERP, League Statistics, Bookshelf API, AskMate OOP

**Verify at:** (general architecture; e.g. Spring guides, "Building REST services")

### OOP-ARCH-05
**Question:** What is a service class?

**A good answer covers**
- holds business logic / use cases
- coordinates models and data access (repositories, DAOs)
- sits between controller / UI and data layer
- easy to unit test with mocked dependencies

**Common misconceptions**
- service = anything that isn't a model

**Interviewer follow-ups**
- "What belongs in the service and not in the controller?"

**Practised in:** Mighty text adventure, Secure ERP, Bookshelf API

**Verify at:** Spring docs, `@Service`; Martin Fowler, "Service Layer"

### OOP-ARCH-06
**Question:** Explain the Open/Closed principle.

**A good answer covers**
- open for extension, closed for modification
- add new behaviour by adding code (new class), not editing existing code
- achieved with abstractions / polymorphism
- example: new type behind an interface instead of a new `switch` branch

**Common misconceptions**
- "code should never be changed"

**Interviewer follow-ups**
- "Show me where adding a feature didn't require changing old code."

**Practised in:** Fly that drone, Enigma, StockTrader

**Verify at:** Robert C. Martin, "The Open-Closed Principle"

### OOP-ARCH-07
**Question:** Explain the Liskov Substitution Principle.

**A good answer covers**
- a subtype must be usable wherever its parent type is expected, without breaking behaviour
- don't strengthen preconditions or weaken guarantees
- classic counter-example: square / rectangle
- a test: does code using the parent still work with the child?

**Common misconceptions**
- "LSP = a subclass must not override anything"

**Interviewer follow-ups**
- "A subclass throws an exception for a method the parent supports. What's wrong?"

**Practised in:** Starfleet Control, Life of the Ants

**Verify at:** Barbara Liskov & Jeannette Wing, "A Behavioral Notion of Subtyping"; R. C. Martin, "The Liskov Substitution Principle"

### OOP-ARCH-08
**Question:** Explain the Dependency Inversion Principle.

**A good answer covers**
- high-level modules depend on abstractions, not on low-level details
- details implement those abstractions
- often realised with dependency injection
- makes testing and swapping implementations easy

**Common misconceptions**
- dependency inversion and dependency injection are the same thing

**Interviewer follow-ups**
- "How did injecting a dependency make a class testable in your project?"

**Practised in:** Phone book, StockTrader, Bookshelf API, Magic 8 Ball

**Verify at:** Robert C. Martin, "The Dependency Inversion Principle"
