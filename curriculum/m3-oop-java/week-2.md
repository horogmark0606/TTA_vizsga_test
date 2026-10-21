# OOP with Java — Structure and principles

> Project cards for Week 2 — Structure and principles. Concept level only: no project descriptions,
> tasks or solutions. Question IDs point to topics in `questions/index.yaml`.
> Status: drafted 2026-10-19; mentor review in progress.

## Week 2 — Structure and principles

### OOP · Fly that drone (solo, week 2)

**Concepts to understand**
- The Open/Closed Principle: adding new behaviour without changing existing code.
- Polymorphism: each kind of movement as its own class behind a common interface.
- Single responsibility per class.
- Parameterised unit tests: one test, many cases.

**Typical pitfalls**
- A growing `switch` that has to be edited for every new movement.

**Explain-your-own-code prompts**
- "Add a new kind of movement. Which files do you touch, and which don't you touch?"
- "How does your parameterised test get its cases?"

**Related questions:** OOP-ARCH-06, OOP-ARCH-01, OOP-TYPE-09, OOP-TEST-03

### OOP · Mighty text adventure (team, week 2)

**Concepts to understand**
- Data classes vs. service / logic classes.
- MVC: keeping display separate from game logic.
- Modelling a game world: areas, connections, actions, the player.
- Single Responsibility Principle.
- Input handling: case-insensitive commands, short and long forms, help.
- Win / lose checks every turn.

**Typical pitfalls**
- Printing from inside the logic classes.
- One huge class that does everything.

**Explain-your-own-code prompts**
- "Which classes would change if you replaced the console with a web UI?"
- "How does an action lead the player into another area? Show me in your data."

**Related questions:** OOP-ARCH-01, OOP-ARCH-04, OOP-ARCH-05, OOP-TYPE-06

### OOP · Project Codewars - 7 kyu in Java (solo, week 2)

**Concepts to understand**
- Short algorithmic exercises: strings, arrays, loops, conditionals, methods.
- Reading a problem statement precisely, including edge cases.
- Working against hidden tests.
- Learning from other people's solutions after solving.

**Typical pitfalls**
- Solving only the visible examples.

**Explain-your-own-code prompts**
- "Pick one kata. Walk me through your solution, then through a better one you saw afterwards."

**Related questions:** OOP-LANG-02, OOP-LANG-03, OOP-LANG-05, OOP-TYPE-23
