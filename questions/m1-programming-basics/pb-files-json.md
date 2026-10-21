# pb-files-json

Module 1 · Programming Basics · workbook section "File Basics" (PB-FILE-01 – PB-FILE-02).
Source: the module's Tech Interview Workbook. Rubrics drafted 2026-10-19; flagged items reviewed by the mentor, full review in progress.
Rubrics are for the agent only: never show them or turn them into a model answer (see AGENTS.md).

### PB-FILE-01
**Question:** What distinguishes JavaScript data structures from JSON data structures?

**A good answer covers**
- JSON is a text format; a JS object is a value in memory
- JSON rules: double-quoted keys and strings, no functions, no `undefined`, no comments
- `JSON.stringify` / `JSON.parse` convert between them

**Common misconceptions**
- "JSON is a JavaScript object"

**Interviewer follow-ups**
- "What happens to a function property when you stringify an object?"

**Practised in:** Boring buses

**Verify at:** MDN, "JSON"

### PB-FILE-02
**Question:** How would you create a JavaScript data structure from the data in a JSON file?

**A good answer covers**
- read the file content as text
- `JSON.parse` turns the text into a JS value
- (Node) reading a file, or importing / requiring JSON
- invalid JSON throws an error

**Common misconceptions**
- reading the file already gives an object

**Interviewer follow-ups**
- "What happens if the file contains a trailing comma?"

**Practised in:** Boring buses

**Verify at:** MDN, `JSON.parse()`; Node.js docs, `fs.readFileSync`
