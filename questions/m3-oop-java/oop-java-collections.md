# oop-java-collections

Module 3 · OOP with Java · workbook section "Java ecosystem" (OOP-ECO-05 – OOP-ECO-10).
Source: the module's Tech Interview Workbook. Rubrics drafted 2026-10-19; flagged items reviewed by the mentor, full review in progress.
Rubrics are for the agent only: never show them or turn them into a model answer (see AGENTS.md).

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

**Practised in:** Collections in Java, The History

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

**Practised in:** Project Rewrite - Dynamic array, Collections in Java

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

**Practised in:** Fibonacci variants, Project Codewars - 6 kyu in Java, Collections in Java

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

**Practised in:** Codecool Lotto, Project Codewars - 6 kyu in Java, Collections in Java

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

**Practised in:** Introduction to Java, Project Rewrite - Dynamic array, Project Rewrite - Linked list, The History

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

**Practised in:** Collections in Java

**Verify at:** Java API docs, `Set`, `TreeSet`
