# gen-java

General module · Java extras.
**General, not course-reviewed:** extra questions that fill gaps the workbooks leave. Not from the course;
kept from the repo's original question bank. Rubrics are for the agent only (see AGENTS.md).

### GEN-JAVA-01
**Question:** Checked vs unchecked exceptions?

**A good answer covers**
- checked (extends `Exception`) must be handled/declared
- unchecked (`RuntimeException`) not
- examples IOException vs NullPointerException.

**Interviewer follow-ups**
- Which would you use for invalid user input?

**Practised in:** (general; not tied to a course project)

_Difficulty: easy · original id: je-j1_

### GEN-JAVA-02
**Question:** How do `try/catch/finally` and try-with-resources work?

**A good answer covers**
- finally always runs
- try-with-resources auto-closes `AutoCloseable`
- multiple catch blocks, specific first.

**Interviewer follow-ups**
- What does `throw` vs `throws` mean?

**Practised in:** (general; not tied to a course project)

_Difficulty: easy · original id: je-j2_

### GEN-JAVA-03
**Question:** How do you create and use a custom exception? What is a good practice for catching?

**A good answer covers**
- extend `Exception`/`RuntimeException`
- meaningful message + cause
- don't swallow exceptions
- catch specific types.

**Interviewer follow-ups**
- What is wrong with an empty catch block?

**Practised in:** (general; not tied to a course project)

_Difficulty: medium · original id: je-j3_

### GEN-JAVA-04
**Question:** How does a `HashMap` work at a high level?

**A good answer covers**
- hashCode -> bucket
- equals to find key
- collisions
- average O(1)
- needs consistent `equals`/`hashCode`.

**Interviewer follow-ups**
- What breaks if a key class overrides only `equals`?

**Practised in:** (general; not tied to a course project)

_Difficulty: medium · original id: jc-03_

### GEN-JAVA-05
**Question:** What are generics and why use them?

**A good answer covers**
- type parameters (`List<String>`)
- compile-time type safety, no casts
- reusable code.

**Interviewer follow-ups**
- Why can't you write `List<int>`?

**Practised in:** (general; not tied to a course project)

_Difficulty: medium · original id: jc-04_

### GEN-JAVA-06
**Question:** Stack vs heap: what lives where? What does the garbage collector do?

**A good answer covers**
- stack = local vars/primitives/references per call
- heap = objects
- GC frees unreachable objects.

**Interviewer follow-ups**
- Can you cause a memory leak in Java?

**Practised in:** (general; not tied to a course project)

_Difficulty: medium · original id: jm-03_

### GEN-JAVA-07
**Question:** Is Java pass-by-value or pass-by-reference?

**A good answer covers**
- always by value
- for objects the reference is copied
- can mutate object, can't reassign caller's variable.

**Interviewer follow-ups**
- Why are `String`s immutable?

**Practised in:** (general; not tied to a course project)

_Difficulty: medium · original id: jm-04_
