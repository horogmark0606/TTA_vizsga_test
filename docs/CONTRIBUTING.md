# Extending the repo

## Content rules (read before adding anything)

- **No course IP.** Never paste project descriptions, task wording, acceptance criteria, starter or
  reference code, or spec-specific names (required class / function / file names, exact messages, sample data).
  Project cards stay at concept level: someone who did the project recognises it; someone who didn't can't build it from the card.
- **Rubrics, not model answers.** "A good answer covers" lists 3–5 terse points (keywords, short phrases),
  never full sentences that read like an answer.
- **Course vs general.** Workbook topics (`source: workbook` in `questions/index.yaml`) hold the course's own
  questions with mentor-owned rubrics; don't add your own questions to them. Put new questions into a `gen` topic or a new topic marked
  "general, not course-reviewed".
- "Verify at" must be a public, authoritative source (MDN, official docs, Pro Git, …), never a course page.
  If there is none, write: `(no single authoritative source; judge by the rubric and the student's own example, don't search)`.

## Question rubric format (`questions/<module>/<topic-id>.md`)

```markdown
### PB-FN-05
**Question:** <question text>

> Note for the agent: <optional: an exception for this question, e.g. "accept the older answer, mention what changed">

**A good answer covers**
- 3–5 terse points

**Common misconceptions**
- 1–2 items, or "(none typical)"

**Interviewer follow-ups**
- 1–2 questions

**Practised in:** <project titles from curriculum/, or "(no project; theory only)">

**Verify at:** <public source>
```

Ids: `<PREFIX>-<SECTION>-<nn>`, unique, never renumbered; append new ones. `GEN-<AREA>-<nn>` for general extras.
After adding, update `count` and `ids` in `questions/index.yaml`.

## Project card format (`curriculum/<module>/<week>.md`)

```markdown
### PB · Hangman (team, week 1)

**Concepts to understand**
- 4–8 bullets, concept level, own words

**Typical pitfalls**
- 1–4 generic beginner mistakes

**Explain-your-own-code prompts**
- 2–4 questions the student answers about *their own* code

**Related questions:** PB-ALG-05, PB-DATA-05
```

The title must match the project's real title. Keep "Related questions" on the card and "Practised in"
on the rubric in sync by hand, and add the project to the topic's line in `curriculum/INDEX.md`.

## Size

- Hand-written files: keep under ~150 lines.
- Rubric and card files have a fixed structure (~15–20 lines per entry) and may reach ~250 lines.
  Split a topic into two meaningful topics beyond that and update the index files.

## New topic checklist
1. `questions/<module>/<topic-id>.md`
2. Row in `questions/index.yaml` (id, module, file, count, ids, source, tags)
3. Entry in `progress/topics.yaml` (score 0)
4. Line in `curriculum/INDEX.md`

## New module (e.g. HR / behavioral)
Create `questions/<module>/`, add topics as above. For behavioral questions use the same format; put the
STAR structure into "A good answer covers". Add a method in `methods/` (e.g. `star-practice.md`) and list it in `methods/README.md`.

## New method
Create `methods/<name>.md` with: When / Steps / Persist. Add a row in `methods/README.md`.

## Keep it token-efficient
- Index files stay one line per item.
- Never put bulk content in AGENTS.md or index files; link to it.
- Prefer many small files over a few large ones.
