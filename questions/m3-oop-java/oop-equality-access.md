# oop-equality-access

Module 3 · OOP with Java · workbook section "Type system" (OOP-TYPE-19 – OOP-TYPE-26).
Source: the module's Tech Interview Workbook. Rubrics drafted 2026-10-19; flagged items reviewed by the mentor, full review in progress.
Rubrics are for the agent only: never show them or turn them into a model answer (see AGENTS.md).

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

**Practised in:** Wardrobe

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

**Practised in:** Geometry, Waste Recycling

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

**Practised in:** Waste Recycling

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

**Practised in:** Project Rewrite - Linked list

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

**Practised in:** Introduction to Java, Project Codewars - 7 kyu in Java

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

**Practised in:** (no project; theory only)

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

**Practised in:** (no project; theory only)

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

**Practised in:** Wardrobe

**Verify at:** Java API docs, module `java.base`
