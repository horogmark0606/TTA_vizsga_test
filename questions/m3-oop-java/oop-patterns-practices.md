# oop-patterns-practices

Module 3 · OOP with Java · workbook section "Architecture" (OOP-ARCH-09 – OOP-ARCH-15).
Source: the module's Tech Interview Workbook. Rubrics drafted 2026-10-19; flagged items reviewed by the mentor, full review in progress.
Rubrics are for the agent only: never show them or turn them into a model answer (see AGENTS.md).

### OOP-ARCH-09
**Question:** What do we mean by the Gang of Four (GoF) Design Patterns? Can you name some of these patterns?

**A good answer covers**
- 23 patterns from the 1994 book *Design Patterns* (Gamma, Helm, Johnson, Vlissides)
- three groups: creational, structural, behavioural
- examples: Factory Method, Singleton, Builder, Adapter, Decorator, Strategy, Observer
- reusable solutions to recurring design problems

**Common misconceptions**
- patterns are ready-made code to copy

**Interviewer follow-ups**
- "Which pattern did you use in a project, maybe without naming it?"

**Practised in:** Enigma

**Verify at:** refactoring.guru, "Design Patterns"

### OOP-ARCH-10
**Question:** What are the risks associated with using the GoF design patterns?

**A good answer covers**
- over-engineering: patterns where simple code would do
- extra indirection makes code harder to read
- wrong pattern for the problem
- some are seen as anti-patterns in some contexts (Singleton → hidden global state)

**Common misconceptions**
- "more patterns = better design"

**Interviewer follow-ups**
- "Why is a Singleton hard to test?"

**Practised in:** (no project; theory only)

**Verify at:** refactoring.guru, pattern pages ("Pros and Cons")

### OOP-ARCH-11
**Question:** What do we mean by YAGNI?

**A good answer covers**
- "You Aren't Gonna Need It"
- don't build features / abstractions before they are needed
- reduces complexity and wasted work
- from Extreme Programming

**Common misconceptions**
- YAGNI means "don't design at all"

**Interviewer follow-ups**
- "Tell me about something you built 'just in case'."

**Practised in:** (no project; theory only)

**Verify at:** Martin Fowler, "Yagni" (martinfowler.com)

### OOP-ARCH-12
**Question:** What do we mean by SLAP?

**A good answer covers**
- Single Level of Abstraction Principle
- each method's statements should be at the same level of abstraction
- high-level method reads like a list of steps; details go into helpers
- improves readability

**Common misconceptions**
- confusing it with SRP

**Interviewer follow-ups**
- "Show me a method that mixes high-level steps and low-level details."

**Practised in:** Bonus in the air

**Verify at:** (no single authoritative source; judge by the rubric and the student's own example, don't search)

### OOP-ARCH-13
**Question:** What do we mean by KISS?

**A good answer covers**
- "Keep It Simple, Stupid"
- prefer the simplest solution that works
- simpler code is easier to read, test and change

**Common misconceptions**
- simple = short / clever one-liners

**Interviewer follow-ups**
- "When does a 'clever' solution violate KISS?"

**Practised in:** (no project; theory only)

**Verify at:** (no single authoritative source; judge by the rubric and the student's own example, don't search)

### OOP-ARCH-14
**Question:** What is the Repository Pattern?

**A good answer covers**
- an abstraction over data access that looks like a collection of domain objects
- hides how and where data is stored (SQL, files, memory)
- services talk to the repository interface
- easy to swap or mock in tests

**Common misconceptions**
- repository = the database

**Interviewer follow-ups**
- "What's the difference between your DAO and a repository?"

**Practised in:** Book DB, AskMate OOP

**Verify at:** Martin Fowler, *P of EAA*, "Repository"

### OOP-ARCH-15
**Question:** What is a CRUD interface?

**A good answer covers**
- Create, Read, Update, Delete operations for an entity
- as an interface: e.g. `save`, `findById`, `findAll`, `update`, `delete`
- maps to SQL (`INSERT`, `SELECT`, `UPDATE`, `DELETE`) and to HTTP methods
- generic version for many entities

**Common misconceptions**
- (none typical)

**Interviewer follow-ups**
- "How would you make one CRUD interface work for several entity types?"

**Practised in:** Book DB, Secure ERP, Bookshelf API, AskMate OOP

**Verify at:** Spring Data docs, `CrudRepository`
