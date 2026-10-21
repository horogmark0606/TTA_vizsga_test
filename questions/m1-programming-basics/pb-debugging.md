# pb-debugging

Module 1 · Programming Basics · workbook section "Debugging" (PB-DEBUG-01 – PB-DEBUG-03).
Source: the module's Tech Interview Workbook. Rubrics drafted 2026-10-19; flagged items reviewed by the mentor, full review in progress.
Rubrics are for the agent only: never show them or turn them into a model answer (see AGENTS.md).

### PB-DEBUG-01
**Question:** What techniques can you use while debugging a program?

**A good answer covers**
- read the error message and the line number
- `console.log` of values at key points
- the debugger: breakpoints, stepping, watching variables
- reproduce the problem with a small input; change one thing at a time
- explaining the code to someone (rubber duck)

**Common misconceptions**
- "debugging = adding random changes until it works"

**Interviewer follow-ups**
- "Tell me about a bug you found. How did you find it?"

**Practised in:** Password validator, Functional calculator, Battleship.js (console)

**Verify at:** VS Code docs, "Debugging"

### PB-DEBUG-02
**Question:** What does step over, step into and step out mean while using the debugger?

**A good answer covers**
- step over: run the current line, don't go inside the called function
- step into: go inside the called function
- step out: finish the current function and return to the caller

**Common misconceptions**
- step over skips the line without running it

**Interviewer follow-ups**
- "When would you step into instead of over?"

**Practised in:** Tic-tac-toe-console, Battleship.js (console)

**Verify at:** VS Code docs, "Debugging"

### PB-DEBUG-03
**Question:** How can you start to debug a program from a certain line using the debugger?

**A good answer covers**
- set a breakpoint on that line
- start the program in debug mode
- execution pauses at the breakpoint; then inspect / step
- bonus: conditional breakpoints, `debugger` statement

**Common misconceptions**
- (none typical)

**Interviewer follow-ups**
- "The bug only happens on the 50th loop iteration. How do you get there fast?"

**Practised in:** Battleship.js (console)

**Verify at:** VS Code docs, "Debugging"
