# oop-unit-testing

Module 3 · OOP with Java · workbook section "Unit testing" (OOP-TEST-01 – OOP-TEST-06).
Source: the module's Tech Interview Workbook. Rubrics drafted 2026-10-19; flagged items reviewed by the mentor, full review in progress.
Rubrics are for the agent only: never show them or turn them into a model answer (see AGENTS.md).

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

**Practised in:** Math formulas, Encrypted letters, Crash test, Bonus in the air, Histogram, AskMate OOP

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

**Practised in:** Math formulas, Crash test, Bonus in the air, Histogram

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

**Practised in:** Fly that drone, Histogram

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

**Practised in:** (no project; theory only)

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

**Practised in:** Phone book, StockTrader, Mockulator, Magic 8 Ball

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

**Practised in:** Phone book, StockTrader, Mockulator

**Verify at:** Martin Fowler, "Mocks Aren't Stubs"
