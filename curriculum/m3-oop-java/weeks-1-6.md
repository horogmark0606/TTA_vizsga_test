# OOP with Java — Ongoing practice

> Project cards for Weeks 1–6 — Ongoing practice. Concept level only: no project descriptions,
> tasks or solutions. Question IDs point to topics in `questions/index.yaml`.
> Status: drafted 2026-10-19; mentor review in progress.

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
