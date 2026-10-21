# oop-classes-types

Module 3 · OOP with Java · workbook section "Type system" (OOP-TYPE-01 – OOP-TYPE-09).
Source: the module's Tech Interview Workbook. Rubrics drafted 2026-10-19; flagged items reviewed by the mentor, full review in progress.
Rubrics are for the agent only: never show them or turn them into a model answer (see AGENTS.md).

### OOP-TYPE-01
**Question:** What are primitive types in Java? Give some examples.

**A good answer covers**
- the eight: `byte`, `short`, `int`, `long`, `float`, `double`, `char`, `boolean`
- hold the value directly, not a reference
- have fixed sizes and defaults
- can't be `null`

**Common misconceptions**
- `String` is a primitive

**Interviewer follow-ups**
- "What's the default value of an `int` field? And of a local `int`?"

**Practised in:** Introduction to Java, Java basics, User Management, Math formulas, Encrypted letters

**Verify at:** dev.java, "Primitive Types"

### OOP-TYPE-02
**Question:** What is the difference between primitive types and reference types?

**A good answer covers**
- primitive variables hold the value; reference variables hold a reference to an object
- references can be `null`
- assignment copies the value vs. copies the reference
- generics need reference types (wrappers, autoboxing)

**Common misconceptions**
- passing an object to a method copies the object

**Interviewer follow-ups**
- "A method changes a field of an object it received. Does the caller see the change?"

**Practised in:** Java basics, Project Rewrite - Linked list

**Verify at:** dev.java, "Primitive Types"; JLS ch. 4

### OOP-TYPE-03
**Question:** What is a class in Java?

**A good answer covers**
- a blueprint / type definition: fields (state) and methods (behaviour)
- objects are created from it
- constructors, access modifiers
- encapsulation

**Common misconceptions**
- a class and an object are the same

**Interviewer follow-ups**
- "Show me a class from your project and explain its responsibility."

**Practised in:** What is OOP?, Diligent Deliveries

**Verify at:** dev.java, "Classes and Objects"

### OOP-TYPE-04
**Question:** What is an object in Java?

**A good answer covers**
- an instance of a class, created with `new`
- has its own state (field values) and shares behaviour (methods)
- lives on the heap, accessed through references
- identity vs. equality

**Common misconceptions**
- (none typical)

**Interviewer follow-ups**
- "Two objects have the same field values. Are they the same object?"

**Practised in:** What is OOP?, Diligent Deliveries

**Verify at:** dev.java, "Classes and Objects"

### OOP-TYPE-05
**Question:** What is a constructor?

**A good answer covers**
- special method that initialises a new object; same name as the class, no return type
- runs on `new`
- can be overloaded; `this(…)` and `super(…)`
- default constructor exists only if you declare none

**Common misconceptions**
- a class always has a no-argument constructor

**Interviewer follow-ups**
- "You add a constructor with parameters. What happens to `new MyClass()`?"

**Practised in:** Diligent Deliveries

**Verify at:** dev.java, "Providing Constructors for your Classes"

### OOP-TYPE-06
**Question:** What is an `enum` in Java?

**A good answer covers**
- a type with a fixed set of named constants
- type-safe alternative to string / int constants
- can have fields, constructors, methods
- works in `switch`; `values()`, `valueOf()`

**Common misconceptions**
- enums are just ints

**Interviewer follow-ups**
- "Where did an enum make your code safer?"

**Practised in:** Mighty text adventure

**Verify at:** dev.java, "Enums"

### OOP-TYPE-07
**Question:** Explain the difference between a class and an enum.

**A good answer covers**
- a class can have any number of instances; an enum has a fixed, predefined set
- enum constructors are private; you can't `new` an enum
- enums can't extend other classes (they implicitly extend `Enum`)
- both can have fields and methods

**Common misconceptions**
- enums can't have methods

**Interviewer follow-ups**
- "When would you turn an enum into a class?"

**Practised in:** (no project; theory only)

**Verify at:** dev.java, "Enums"

### OOP-TYPE-08
**Question:** Explain the difference between a class and a record.

**A good answer covers**
- record: a compact, immutable data carrier (Java 16+)
- auto-generated constructor, accessors, `equals`, `hashCode`, `toString`
- fields are final; records can't extend classes
- a class is general-purpose, mutable if you want

**Common misconceptions**
- records are just shorter classes with setters

**Interviewer follow-ups**
- "Which of your model classes could be a record? Which couldn't?"

**Practised in:** (no project; theory only)

**Verify at:** dev.java, "Using Record to Model Immutable Data"

### OOP-TYPE-09
**Question:** What are interfaces? Why should we use them?

**A good answer covers**
- a contract: method signatures a class promises to implement
- a class can implement many interfaces
- enable polymorphism and loose coupling (code against the interface)
- easier testing (swap in a test double)
- default and static methods

**Common misconceptions**
- interfaces can't contain any method bodies (default methods can)

**Interviewer follow-ups**
- "Where did an interface let you swap one implementation for another?"

**Practised in:** Fly that drone, Enigma, The History, Mockulator

**Verify at:** dev.java, "Interfaces"
