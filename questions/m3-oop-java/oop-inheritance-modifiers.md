# oop-inheritance-modifiers

Module 3 · OOP with Java · workbook section "Type system" (OOP-TYPE-10 – OOP-TYPE-18).
Source: the module's Tech Interview Workbook. Rubrics drafted 2026-10-19; flagged items reviewed by the mentor, full review in progress.
Rubrics are for the agent only: never show them or turn them into a model answer (see AGENTS.md).

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

**Practised in:** What is OOP?, Car Race, Planning motors, Waste Recycling, Starfleet Control

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

**Practised in:** (no project; theory only)

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

**Practised in:** Java basics, Geometry

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

**Practised in:** Java basics

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

**Practised in:** Geometry, Wardrobe

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

**Practised in:** Car Race, Geometry, Planning motors, Starfleet Control, Life of the Ants

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

**Practised in:** User Management

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

**Practised in:** Car Race, Geometry, Waste Recycling, Life of the Ants, League Statistics

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

**Practised in:** User Management

**Verify at:** dev.java, "Overriding and Hiding Methods"
