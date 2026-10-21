# web-testing

Module 2 · Web Frameworks · workbook section "Testing Basics" (WEB-TEST-01 – WEB-TEST-08).
Source: the module's Tech Interview Workbook. Rubrics drafted 2026-10-19; flagged items reviewed by the mentor, full review in progress.
Rubrics are for the agent only: never show them or turn them into a model answer (see AGENTS.md).

### WEB-TEST-01
**Question:** What is a test case?

**A good answer covers**
- one specific scenario: given input / state, expected result
- runs automatically and gives pass / fail
- named after the behaviour it checks

**Common misconceptions**
- a test case = a test file

**Interviewer follow-ups**
- "Give me three test cases for a function that checks a password."

**Practised in:** Testing basics, We test

**Verify at:** Vitest docs, "Getting Started"

### WEB-TEST-02
**Question:** What are the advantages of writing unit tests?

**A good answer covers**
- catch bugs early, close to where they are
- safe refactoring (regression protection)
- document expected behaviour
- push towards smaller, testable functions
- fast feedback

**Common misconceptions**
- "tests prove there are no bugs"

**Interviewer follow-ups**
- "When did a test save you from a bug?"

**Practised in:** Testing basics

**Verify at:** Martin Fowler, "Unit Test" (martinfowler.com)

### WEB-TEST-03
**Question:** What is an assertion? Give some examples.

**A good answer covers**
- a statement that checks an expected condition and fails the test if it is false
- `expect(x).toBe(…)`, `toEqual`, `toContain`, `toThrow`, `toBeTruthy`
- a test can have several, but ideally checks one behaviour

**Common misconceptions**
- (none typical)

**Interviewer follow-ups**
- "How do you assert that a function throws?"

**Practised in:** Testing basics, We test

**Verify at:** Vitest docs, "expect"

### WEB-TEST-04
**Question:** What is the arrange/act/assert pattern?

**A good answer covers**
- arrange: set up input and state
- act: call the code under test
- assert: check the result
- makes tests readable and focused

**Common misconceptions**
- several act steps in one test

**Interviewer follow-ups**
- "Point out the three parts in one of your tests."

**Practised in:** We test

**Verify at:** (no single authoritative source; judge by the rubric and the student's own example, don't search)

### WEB-TEST-05
**Question:** What is code coverage? Why is it used?

**A good answer covers**
- the share of code (lines, branches, functions) executed by the tests
- shows untested parts
- high coverage ≠ good tests (assertions may be weak)
- branch coverage is stricter than line coverage

**Common misconceptions**
- 100% coverage means bug-free

**Interviewer follow-ups**
- "How can you have 100% coverage and still miss a bug?"

**Practised in:** Testing basics

**Verify at:** Vitest docs, "Coverage"

### WEB-TEST-06
**Question:** How do you test asynchronous code with Vitest?

**A good answer covers**
- make the test function `async` and `await` the code
- or return the Promise
- `expect(promise).resolves` / `.rejects`
- mocking / faking slow dependencies (fetch, timers)

**Common misconceptions**
- forgetting `await`, so the test passes before the assertion runs

**Interviewer follow-ups**
- "Your async test always passes, even when it shouldn't. What's the likely cause?"

**Practised in:** (no project; theory only)

**Verify at:** Vitest docs, "expect" (resolves / rejects)

### WEB-TEST-07
**Question:** What is `setup` & `teardown` in Vitest?

**A good answer covers**
- code run before / after tests: `beforeEach`, `afterEach`, `beforeAll`, `afterAll`
- setup prepares a fresh state; teardown cleans up
- keeps tests independent

**Common misconceptions**
- tests can depend on the order they run in

**Interviewer follow-ups**
- "Why `beforeEach` instead of `beforeAll` for resetting data?"

**Practised in:** (no project; theory only)

**Verify at:** Vitest docs, "Setup and Teardown"

### WEB-TEST-08
**Question:** Give an example when you would use in Vitest's the `toBe` & `toEqual` assertions.

**A good answer covers**
- `toBe`: strict identity (`Object.is`); for primitives or the same object reference
- `toEqual`: deep equality of content; for objects and arrays
- `expect([1]).toBe([1])` fails, `toEqual` passes

**Common misconceptions**
- they are interchangeable

**Interviewer follow-ups**
- "Which one for checking a function's returned array?"

**Practised in:** We test

**Verify at:** Vitest docs, "expect" (toBe, toEqual)
