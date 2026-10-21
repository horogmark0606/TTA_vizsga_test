# OOP with Java — interview question rubrics

> Questions come from the module's Tech Interview Workbook (students already
> have them). Rubrics are for the agent only: compare silently, never show
> them, never turn them into a model answer. See the agent instructions.
> Which projects practise each question: `OOP-index.md`.
>
> Status: **draft, mentor review pending.**

---

## Java ecosystem

### OOP-ECO-01
**Question:** What is the JVM?

**A good answer covers**
- the Java Virtual Machine runs compiled bytecode
- platform independence: same bytecode, a JVM per OS ("write once, run anywhere")
- memory management with garbage collection
- JIT compilation to native code at runtime

**Common misconceptions**
- "the JVM runs `.java` source files"

**Interviewer follow-ups**
- "Why can other languages (Kotlin, Scala) run on the JVM?"

**Verify at:** Oracle, "The Java Virtual Machine Specification" (introduction); dev.java, "Getting Started"

### OOP-ECO-02
**Question:** What does Java compilation mean?

**A good answer covers**
- `javac` turns `.java` source into `.class` bytecode
- type checks and syntax errors are caught at compile time
- the JVM then runs the bytecode (with JIT at runtime)
- build tools (Maven, Gradle) run this for you

**Common misconceptions**
- Java compiles straight to machine code

**Interviewer follow-ups**
- "Name an error the compiler catches and one it can't."

**Verify at:** dev.java, "Compiling and running a Java program"

### OOP-ECO-03
**Question:** What is Java bytecode?

**A good answer covers**
- the instruction set of the JVM, stored in `.class` files
- platform-independent intermediate code
- interpreted or JIT-compiled by the JVM

**Common misconceptions**
- bytecode is readable Java

**Interviewer follow-ups**
- "Where do the `.class` files end up in your project?"

**Verify at:** Oracle, "The Java Virtual Machine Specification", ch. 1

### OOP-ECO-04
**Question:** What is the difference between the JRE and the JDK?

**A good answer covers**
- JRE: what you need to **run** Java (JVM + core libraries)
- JDK: JRE + development tools (`javac`, debugger, `jar`, …)
- developers install the JDK
- (modern Java distributes the JDK; a separate JRE is less common)

**Common misconceptions**
- JDK and JVM are the same

**Interviewer follow-ups**
- "What does a server that only runs your app need?"

**Verify at:** Oracle / dev.java, JDK documentation overview

### OOP-ECO-05
**Question:** What is the `Iterable` interface?

**A good answer covers**
- an object you can iterate over; provides an `Iterator`
- makes the enhanced for-each loop work
- the root of the collection hierarchy (`Collection` extends it)
- `forEach` default method

**Common misconceptions**
- `Map` is an `Iterable` (it isn't directly)

**Interviewer follow-ups**
- "How would you make your own class usable in a for-each loop?"

**Verify at:** Java API docs, `java.lang.Iterable`

### OOP-ECO-06
**Question:** What is the `Collection` interface?

**A good answer covers**
- the root interface for groups of elements (`List`, `Set`, `Queue`)
- common operations: `add`, `remove`, `contains`, `size`, `isEmpty`, iteration
- `Map` is **not** a `Collection`
- programming to the interface, not the implementation

**Common misconceptions**
- `Map` extends `Collection`

**Interviewer follow-ups**
- "Why declare `List<String> x = new ArrayList<>()` instead of `ArrayList<String> x`?"

**Verify at:** Java API docs, `java.util.Collection`; dev.java, "The Collections Framework"

### OOP-ECO-07
**Question:** What is the `Map` interface?

**A good answer covers**
- key → value pairs; keys are unique
- `put`, `get`, `containsKey`, `remove`, `entrySet` / `keySet` / `values`
- implementations: `HashMap`, `TreeMap` (sorted), `LinkedHashMap` (insertion order)
- keys rely on `equals` and `hashCode`

**Common misconceptions**
- `HashMap` keeps insertion order

**Interviewer follow-ups**
- "What happens when you `put` a key that already exists?"

**Verify at:** Java API docs, `java.util.Map`

### OOP-ECO-08
**Question:** Compare sets, lists, and queues in Java.

**A good answer covers**
- list: ordered, index access, duplicates allowed
- set: no duplicates, usually no index
- queue: ordered for processing (FIFO, or priority), `offer` / `poll` / `peek`
- a use case for each

**Common misconceptions**
- sets keep insertion order (only some implementations do)

**Interviewer follow-ups**
- "Which one for the unique numbers in your lotto draw?"

**Verify at:** dev.java, "The Collections Framework"

### OOP-ECO-09
**Question:** Compare `ArrayList` and `LinkedList` in Java.

**A good answer covers**
- `ArrayList`: backed by a resizable array; fast index access, slow insert / remove in the middle
- `LinkedList`: nodes with references; fast insert / remove at known positions, slow index access
- memory overhead of nodes
- in practice `ArrayList` is usually the default

**Common misconceptions**
- `LinkedList` is always faster for inserting (finding the position costs O(n))

**Interviewer follow-ups**
- "What did your performance tests show, and why?"

**Verify at:** Java API docs, `ArrayList`, `LinkedList`

### OOP-ECO-10
**Question:** Are sets sorted in Java?

**A good answer covers**
- not in general
- `HashSet`: no order guaranteed
- `LinkedHashSet`: insertion order
- `TreeSet` (`SortedSet`): sorted by natural order or a comparator

**Common misconceptions**
- "yes, sets are always sorted"

**Interviewer follow-ups**
- "What does a `TreeSet` need from its elements?"

**Verify at:** Java API docs, `Set`, `TreeSet`

---

## Language features

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

**Verify at:** dev.java, "Lambda Expressions"

---

## Type system

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

**Verify at:** dev.java, "Interfaces"

### OOP-TYPE-10
**Question:** What is inheritance?

**A good answer covers**
- a subclass gets the fields / methods of its parent (`extends`)
- "is-a" relationship
- reuse and specialisation; overriding
- every class ultimately extends `Object`
- risks: tight coupling, fragile hierarchies

**Common misconceptions**
- inheritance is the main way to reuse code

**Interviewer follow-ups**
- "Give me a case where inheritance was the wrong choice."

**Verify at:** dev.java, "Inheritance"

### OOP-TYPE-11
**Question:** Is multiple inheritance allowed in Java?

**A good answer covers**
- not for classes: one superclass only
- a class can implement several interfaces
- why: avoids the "diamond problem" of state
- default-method conflicts must be resolved explicitly

**Common misconceptions**
- "Java has no multiple inheritance of any kind"

**Interviewer follow-ups**
- "Two interfaces have the same default method. What happens?"

**Verify at:** dev.java, "Multiple Inheritance of State, Implementation, and Type"

### OOP-TYPE-12
**Question:** What is a static class member?

**A good answer covers**
- belongs to the class, not to an instance
- shared by all instances; accessed via the class name
- static fields (shared state, constants) and static methods (utilities, factories)
- `main` is static

**Common misconceptions**
- static means "constant"

**Interviewer follow-ups**
- "Why are global mutable static fields risky?"

**Verify at:** dev.java, "Understanding Class Members"

### OOP-TYPE-13
**Question:** Can a static method use non-static members?

**A good answer covers**
- not directly: there is no `this`
- only through an object reference passed in or created
- instance methods can use static members

**Common misconceptions**
- "yes, it can read any field of the class"

**Interviewer follow-ups**
- "Why does calling an instance method from `main` fail to compile?"

**Verify at:** dev.java, "Understanding Class Members"

### OOP-TYPE-14
**Question:** What does the `final` keyword mean in Java?

**A good answer covers**
- final variable / field: assigned once
- final method: can't be overridden
- final class: can't be extended
- a final reference doesn't make the object immutable

**Common misconceptions**
- `final List` means the list can't change

**Interviewer follow-ups**
- "How do you make a class truly immutable?"

**Verify at:** dev.java, "Writing Final Classes and Methods"

### OOP-TYPE-15
**Question:** What does the `abstract` keyword mean in Java?

**A good answer covers**
- abstract class: can't be instantiated; may have abstract and concrete methods, and state
- abstract method: no body; subclasses must implement it
- used for a shared base with forced specialisation
- vs. interface

**Common misconceptions**
- abstract classes can't have constructors

**Interviewer follow-ups**
- "Abstract class or interface: how do you choose?"

**Verify at:** dev.java, "Abstract Methods and Classes"

### OOP-TYPE-16
**Question:** What is _overloading_ in Java?

**A good answer covers**
- several methods with the same name and different parameter lists
- chosen at compile time by the arguments
- return type alone isn't enough
- common for constructors

**Common misconceptions**
- overloading by return type only

**Interviewer follow-ups**
- "`print(int)` and `print(long)`: which is called with `print(5)`?"

**Verify at:** dev.java, "Defining Methods" (Overloading)

### OOP-TYPE-17
**Question:** What is _overriding_ in Java?

**A good answer covers**
- a subclass provides its own version of an inherited method (same signature)
- chosen at runtime by the object's actual type (dynamic dispatch)
- `@Override` annotation
- can't reduce visibility; `super.method()` calls the parent version

**Common misconceptions**
- the reference type decides which version runs

**Interviewer follow-ups**
- "`Animal a = new Dog(); a.speak();` Which method runs, and why?"

**Verify at:** dev.java, "Overriding and Hiding Methods"

### OOP-TYPE-18
**Question:** What is the difference between overloading and overriding?

**A good answer covers**
- overloading: same name, different parameters, same class; compile-time
- overriding: same signature, subclass; runtime
- overriding is what makes polymorphism work

**Common misconceptions**
- they're two names for the same thing

**Interviewer follow-ups**
- "Show me one of each in your code."

**Verify at:** dev.java, "Overriding and Hiding Methods"

### OOP-TYPE-19
**Question:** What is `null`?

**A good answer covers**
- a reference that points to no object
- default for reference fields
- using it causes `NullPointerException`
- `Optional` and validation to avoid it; primitives can't be null

**Common misconceptions**
- `null` is an object

**Interviewer follow-ups**
- "Why return `Optional` instead of `null`?"

**Verify at:** Java API docs, `Optional`; JLS, "The Null Type"

### OOP-TYPE-20
**Question:** Compare the access modifiers in Java.

**A good answer covers**
- `public`: everywhere
- `protected`: package + subclasses
- package-private (no modifier): same package only
- `private`: same class only
- encapsulation: as restrictive as possible

**Common misconceptions**
- `protected` is visible only in subclasses (also the whole package)

**Interviewer follow-ups**
- "Why are fields usually private?"

**Verify at:** dev.java, "Controlling Access to Members of a Class"

### OOP-TYPE-21
**Question:** What is the default access modifier in a class?

**A good answer covers**
- package-private: no keyword written
- visible within the same package only
- (interface members are public by default)

**Common misconceptions**
- the default is `public` (or `private`)

**Interviewer follow-ups**
- "When is package-private a good choice?"

**Verify at:** dev.java, "Controlling Access to Members of a Class"

### OOP-TYPE-22
**Question:** What is the purpose of the `equals()` method?

**A good answer covers**
- logical equality of two objects (content), defined by the class
- default from `Object` compares identity
- override it together with `hashCode`
- used by collections (`contains`, `HashMap` keys)

**Common misconceptions**
- overriding `equals` without `hashCode` is fine

**Interviewer follow-ups**
- "What breaks in a `HashSet` if `hashCode` isn't overridden?"

**Verify at:** Java API docs, `Object.equals()`, `Object.hashCode()`

### OOP-TYPE-23
**Question:** What is the difference between `==` and `equals()`?

**A good answer covers**
- `==` on references compares identity (same object)
- `==` on primitives compares values
- `equals()` compares logical content (if the class overrides it)
- strings: always use `equals`

**Common misconceptions**
- `==` works for strings (it sometimes does because of interning, which is misleading)

**Interviewer follow-ups**
- "Why does `"a" == "a"` sometimes print `true`?"

**Verify at:** Java API docs, `Object.equals()`

### OOP-TYPE-24
**Question:** What is the difference between `long` and `Long`?

**A good answer covers**
- `long`: primitive, 64-bit value, can't be null
- `Long`: wrapper object, can be null, has methods
- autoboxing / unboxing between them
- generics and collections need `Long`
- unboxing a null `Long` throws `NullPointerException`

**Common misconceptions**
- they are interchangeable in every case

**Interviewer follow-ups**
- "Comparing two `Long`s with `==`: what can go wrong?"

**Verify at:** Java API docs, `java.lang.Long`; dev.java, "Autoboxing and Unboxing"

### OOP-TYPE-25
**Question:** Which can store bigger numbers, `long` or `Long`?

**A good answer covers**
- neither: same range (64-bit signed)
- `Long` wraps a `long`
- for bigger numbers: `BigInteger`

**Common misconceptions**
- "`Long` is bigger because it's an object"

**Interviewer follow-ups**
- "What happens when a `long` overflows?"

**Verify at:** Java API docs, `Long.MAX_VALUE`, `BigInteger`

### OOP-TYPE-26
**Question:** What kind of packages do you know under `java.util.*` ? Bring at least 3 examples.

**A good answer covers**
- `java.util` itself: collections, `Optional`, `Scanner`, `Random`, `UUID`
- `java.util.stream`
- `java.util.function`
- `java.util.concurrent`
- `java.util.regex`

**Common misconceptions**
- naming classes only (the question asks about packages)

**Interviewer follow-ups**
- "Which of these did you use, and for what?"

**Verify at:** Java API docs, module `java.base`

---

## Architecture

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

**Verify at:** Robert C. Martin, "The Dependency Inversion Principle"

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

**Verify at:** Spring Data docs, `CrudRepository`

---

## Unit testing

### OOP-TEST-01
**Question:** Why is unit testing a good practice?

**A good answer covers**
- verifies small units in isolation, quickly
- catches regressions; safe refactoring
- documents behaviour
- pushes towards decoupled design

**Common misconceptions**
- unit tests replace all other testing

**Interviewer follow-ups**
- "Which of your classes was hardest to test, and why?"

**Verify at:** Martin Fowler, "Unit Test"

### OOP-TEST-02
**Question:** What is JUnit?

**A good answer covers**
- the standard unit-testing framework for Java (JUnit 5 / Jupiter)
- `@Test`, assertions (`assertEquals`, `assertThrows`)
- lifecycle annotations (`@BeforeEach`, `@AfterAll`, …)
- runs from the IDE and build tools

**Common misconceptions**
- (none typical)

**Interviewer follow-ups**
- "How do you test that a method throws an exception?"

**Verify at:** JUnit 5 User Guide

### OOP-TEST-03
**Question:** What is a parameterized test?

**A good answer covers**
- one test method run with several sets of input / expected values
- avoids copy-pasted tests
- JUnit 5: `@ParameterizedTest` with sources (`@ValueSource`, `@CsvSource`, `@MethodSource`)

**Common misconceptions**
- (none typical)

**Interviewer follow-ups**
- "When is a parameterised test less readable than separate tests?"

**Verify at:** JUnit 5 User Guide, "Parameterized Tests"

### OOP-TEST-04
**Question:** What options do you have in NUnit to create parameterized tests?

> Note for the agent: NUnit is the **.NET** framework; the question was left over from the C# workbook. The course expected students to answer for **JUnit**. Accept either a correct NUnit or a correct JUnit answer. If the student answers for NUnit, also ask for the JUnit equivalent, since that is what a Java interview will ask. Praise noticing the mismatch.

**A good answer covers**
- NUnit: `[TestCase(...)]`, `[TestCaseSource]`, `[Values]`, `[Range]`, `[Random]`
- JUnit equivalents: `@ValueSource`, `@CsvSource`, `@MethodSource`

**Common misconceptions**
- NUnit is a Java tool

**Interviewer follow-ups**
- "What's the JUnit equivalent of `[TestCase]`?"

**Verify at:** NUnit docs, "TestCase"; JUnit 5 User Guide

### OOP-TEST-05
**Question:** What is _mocking_?

**A good answer covers**
- replacing a real dependency with a controllable stand-in in a test
- isolates the unit under test (no DB, network, randomness)
- can verify interactions (was a method called, with what)
- Mockito: `mock`, `when(...).thenReturn(...)`, `verify`

**Common misconceptions**
- mock everything, including the class under test

**Interviewer follow-ups**
- "What's a risk of too much mocking?"

**Verify at:** Mockito documentation

### OOP-TEST-06
**Question:** What is the difference between _mocking_, _stubbing_ and _faking_?

**A good answer covers**
- stub: returns fixed answers; no behaviour checks
- fake: a working but simplified implementation (e.g. in-memory DAO)
- mock: pre-programmed and verifies the expected interactions
- all are "test doubles"

**Common misconceptions**
- they are synonyms

**Interviewer follow-ups**
- "Which did you use in the phone book tests, and why each?"

**Verify at:** Martin Fowler, "Mocks Aren't Stubs"

---

## Databases

### OOP-DB-01
**Question:** What are relational databases? What are their advantages and disadvantages?

**A good answer covers**
- data in tables with rows and columns; relations through keys
- SQL, schema, constraints
- advantages: consistency, ACID transactions, powerful queries / joins
- disadvantages: rigid schema, harder horizontal scaling, object–relational mismatch

**Common misconceptions**
- "relational" refers to the relationships between tables (it refers to relations = tables)

**Interviewer follow-ups**
- "When would you pick a NoSQL database instead?"

**Verify at:** PostgreSQL docs, "Tutorial: Concepts"

### OOP-DB-02
**Question:** How do you associate entities to each other in a relational database model?

**A good answer covers**
- foreign keys referencing primary keys
- one-to-many: FK on the "many" side
- many-to-many: a join table with two FKs
- one-to-one: unique FK

**Common misconceptions**
- storing lists of IDs in one column

**Interviewer follow-ups**
- "Model questions and tags. How many tables?"

**Verify at:** PostgreSQL docs, "Foreign Keys"

### OOP-DB-03
**Question:** What are tables in a relational database?

**A good answer covers**
- a named set of rows with the same columns
- each column has a name and a data type
- rows are records; usually identified by a primary key
- constraints define valid data

**Common misconceptions**
- (none typical)

**Interviewer follow-ups**
- "What does one row in your table represent?"

**Verify at:** PostgreSQL docs, "Table Basics"

### OOP-DB-04
**Question:** What is a _primary key_?

**A good answer covers**
- a column (or columns) uniquely identifying each row
- unique and not null
- one per table
- natural vs. surrogate (generated ID) keys

**Common misconceptions**
- a primary key must be a single integer column

**Interviewer follow-ups**
- "Why are email addresses a risky primary key?"

**Verify at:** PostgreSQL docs, "Constraints" (Primary Keys)

### OOP-DB-05
**Question:** What is a _foreign key_?

**A good answer covers**
- a column referencing the primary key of another (or the same) table
- enforces referential integrity
- defines relationships
- `ON DELETE` behaviour (restrict, cascade, set null)

**Common misconceptions**
- a foreign key must be unique

**Interviewer follow-ups**
- "What happens when you delete a row others refer to?"

**Verify at:** PostgreSQL docs, "Constraints" (Foreign Keys)

### OOP-DB-06
**Question:** What does the SQL abbreviation stand for?

**A good answer covers**
- Structured Query Language
- declarative: you say *what*, the database decides *how*

**Common misconceptions**
- (none typical)

**Interviewer follow-ups**
- "What does 'declarative' mean here?"

**Verify at:** PostgreSQL docs, "The SQL Language"

### OOP-DB-07
**Question:** What are some of the SQL database providers that you’ve heard of?

**A good answer covers**
- PostgreSQL, MySQL / MariaDB, SQLite, Microsoft SQL Server, Oracle
- open-source vs. commercial
- managed cloud versions (e.g. AWS RDS)

**Common misconceptions**
- (none typical)

**Interviewer follow-ups**
- "Why might a small app use SQLite?"

**Verify at:** (vendor sites)

### OOP-DB-08
**Question:** What are SQL data types? Are there any differences in data types between different SQL databases?

**A good answer covers**
- each column has a type: integer types, decimal / numeric, text (`VARCHAR`, `TEXT`), boolean, date / time, …
- the standard defines common types; vendors differ (e.g. PostgreSQL `SERIAL`, `JSONB`, MySQL `TINYINT`)
- choosing types affects storage, validation and comparisons

**Common misconceptions**
- all SQL databases have the same types

**Interviewer follow-ups**
- "Why use `NUMERIC` instead of `FLOAT` for money?"

**Verify at:** PostgreSQL docs, "Data Types"

### OOP-DB-09
**Question:** What are _constraints_ in SQL?

**A good answer covers**
- rules on columns / tables that the database enforces
- `NOT NULL`, `UNIQUE`, `PRIMARY KEY`, `FOREIGN KEY`, `CHECK`, `DEFAULT`
- protect data integrity regardless of the application

**Common misconceptions**
- validation in Java is enough

**Interviewer follow-ups**
- "Write a constraint that keeps prices non-negative."

**Verify at:** PostgreSQL docs, "Constraints"

### OOP-DB-10
**Question:** How can we program different SQL databases in Java?

**A good answer covers**
- JDBC: a standard API; each database provides a driver
- `Connection`, `PreparedStatement`, `ResultSet`
- higher levels: Spring JDBC (`JdbcTemplate`), JPA / Hibernate
- switching databases mostly means switching the driver and URL (SQL dialects may differ)

**Common misconceptions**
- each database needs a completely different Java API

**Interviewer follow-ups**
- "Why `PreparedStatement` rather than `Statement`?"

**Verify at:** Oracle, "JDBC Basics" tutorial

### OOP-DB-11
**Question:** Which SQL statement is used to create tables? Describe the syntax briefly.

**A good answer covers**
- `CREATE TABLE name (column type constraints, …)`
- primary key, not null, defaults, foreign keys
- example

**Common misconceptions**
- (none typical)

**Interviewer follow-ups**
- "How do you add a column to an existing table?"

**Verify at:** PostgreSQL docs, `CREATE TABLE`

### OOP-DB-12
**Question:** Which SQL statement can be used to insert values? Describe the syntax briefly.

**A good answer covers**
- `INSERT INTO table (cols) VALUES (…)`
- several rows at once
- generated IDs (`RETURNING id` in PostgreSQL)
- `INSERT … SELECT`

**Common misconceptions**
- column list can always be omitted safely

**Interviewer follow-ups**
- "How do you get the generated ID back in Java?"

**Verify at:** PostgreSQL docs, `INSERT`

### OOP-DB-13
**Question:** Which SQL statement can be used to update values? Describe the syntax briefly.

**A good answer covers**
- `UPDATE table SET col = value, … WHERE condition`
- without `WHERE` every row changes
- can use expressions and subqueries

**Common misconceptions**
- forgetting the `WHERE` clause is harmless

**Interviewer follow-ups**
- "How do you protect yourself from an accidental full-table update?"

**Verify at:** PostgreSQL docs, `UPDATE`

### OOP-DB-14
**Question:** Which SQL statement can be used to delete rows?. Describe the syntax briefly.

**A good answer covers**
- `DELETE FROM table WHERE condition`
- without `WHERE` all rows go
- foreign keys may block or cascade
- vs. `TRUNCATE` / `DROP TABLE`

**Common misconceptions**
- `DELETE` removes the table

**Interviewer follow-ups**
- "What's the difference between `DELETE`, `TRUNCATE` and `DROP`?"

**Verify at:** PostgreSQL docs, `DELETE`

### OOP-DB-15
**Question:** Which SQL statement can be used to create queries?. Describe the syntax briefly.

**A good answer covers**
- `SELECT cols FROM table WHERE … GROUP BY … HAVING … ORDER BY … LIMIT …`
- logical order of evaluation differs from written order (FROM → WHERE → GROUP BY → HAVING → SELECT → ORDER BY)
- aggregates, aliases, `DISTINCT`

**Common misconceptions**
- using a column alias in `WHERE`

**Interviewer follow-ups**
- "Why can't you use a `SELECT` alias in the `WHERE` clause?"

**Verify at:** PostgreSQL docs, `SELECT`

### OOP-DB-16
**Question:** How can you join tables together in SQL? When should you do it?

**A good answer covers**
- `JOIN … ON` a matching condition (usually FK = PK)
- `INNER` (only matches), `LEFT` / `RIGHT` (keep unmatched from one side), `FULL`
- when the data you need is spread over related tables
- a missing condition causes a cross product

**Common misconceptions**
- `INNER JOIN` keeps rows without a match

**Interviewer follow-ups**
- "Find customers who never placed an order. Which join?"

**Verify at:** PostgreSQL docs, "Joins Between Tables"
