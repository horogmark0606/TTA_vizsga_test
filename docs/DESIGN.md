# Design notes

Why the repo works the way it does. For whoever maintains or extends it. The agent doesn't read `docs/`.
Practical maintenance facts (Windows, the two skill copies, invariants, where the content came from): `MAINTAINING.md`.
Content created 2026-10-19 for the FullStack 2026 course (modules: Programming Basics, Web Frameworks,
OOP with Java, Advanced – DevOps). It's a one-off for this cohort: no content updates are planned. Students use it at the end of the course to
prepare for the trial tech interview, which covers all four modules.
A future round with a different curriculum should reuse the *method*, not the content.

## Goal

Help students prepare for tech interviews in two ways:
- **quiz them** on the module's interview questions;
- **help them**: point back to the projects where they practised a concept, and make them explain their own code.

## Course content and IP

- Everything in the repo is student-visible and may become public.
- So it contains **no course IP**: no project descriptions, task wording, criteria, starter or reference
  code, and no spec-specific names.
- Project cards describe what a project teaches, at concept level.
- The workbook questions are included verbatim, because students already have them.
- Students also already have their own finished project code. The agent turns that into practice: instead of
  reviewing pasted code, it asks the student to explain it, which is what an interviewer does.

## Rubrics, not model answers

Students wrote their own workbook answers during the module, of varying quality.

A finished answer set would replace their own research, and an agent judging from general knowledge would
hallucinate. So each question has a **rubric**:
- 3–5 terse points a good answer covers,
- common misconceptions,
- interviewer follow-ups,
- the projects where the topic was practised,
- a public source to check against.

The agent uses the rubric like this:
- it compares silently,
- it probes for missing points without naming them,
- after two probes it points to a project and the source,
- it never writes the answer.

Why this works:
- **Weak shortcut:** a terse checklist is easy to read but a poor shortcut. Someone who memorises it still
  fails the follow-ups.
- **Grounded:** the agent measures against a list the mentor owns and reviews.
- **Uses existing work:** "check my answer" makes use of the students' own workbook answers.

Teaching ("I don't get X") may explain concepts with generic examples. That isn't the same as handing over
the workbook answer.

## Exceptions per question: "Note for the agent"

A rubric can carry a note that overrides the general rules for that one question. Used for:
- **Source bugs:** e.g. the Java workbook asks about NUnit (.NET). The course expected JUnit, so the agent
  accepts either and asks for JUnit.
- **Facts that changed since the workbook was written:** React's docs dropped the "virtual DOM" wording, Vite's
  JSX tooling changed, Node now allows `require()` of ES modules, and the AWS bastion Quick Start was archived.
  The agent accepts the older answer, mentions what changed, and points to the docs.

## Web search

Only as a last resort: when the rubric doesn't settle it, the agent is genuinely unsure, and a wrong verdict
would mislead the student. Even then, one targeted lookup. The reason is to save students' tokens.

Some principles (KISS, SLAP, Arrange-Act-Assert) have no authoritative source. Their rubric says so, and the
agent judges by the rubric and the student's example without searching.

## Course questions vs general extras

- **`source: workbook` topics:** the course's own questions, with mentor-owned rubrics (review in progress
  since 2026-10-19).
- **`gen` topics:** a few extra questions kept from the repo's original bank. They fill gaps the workbooks
  leave: closures, error handling, Promises, CORS, event delegation, Java exceptions and memory, CI/CD,
  advanced Git. They're marked "general, not course-reviewed", and so is anything students add with
  the `extend` skill.

## Tokens

- The agent loads one topic file and at most one card file at a time (see the token rules in `AGENTS.md`).
- Workbook sections longer than ~10 questions were split into two or three topics.
- Rubric and card files may reach ~250 lines because of their fixed structure.

## Scenarios

The questions are the same for every group, but the interview format isn't. A scenario file describes one
format (sections, budgets, scoring) so the agent can rehearse it; the skills read it only when it matters.
The first one is the FullStack 2026 group's trial interview; a general one comes later. Practical tasks are
practice variants, never the real tasks and never course projects. The agent gives feedback on them but no
reference solution, for the same reason there are no model answers.

## Two ways to use it

- **Main path:** this repo with Claude Code or Codex (`AGENTS.md` + the skills, see `MAINTAINING.md`).
- **Upload path:** `standalone/` holds the same content as 12 combined files plus one instruction file, for
  Claude Projects or ChatGPT (instruction field ≤ 8000 characters, ≤ 20 knowledge files). Students upload one
  module at a time to keep token use down.
- The content was copied once from the reviewed source. Because there are no updates, the two copies can't
  drift apart. If you edit one, edit the other.
