# Maintaining this repo

Facts and invariants a maintainer (human or agent) needs before changing anything. The rationale behind the
design is in `DESIGN.md`; file formats and content rules for new material are in `CONTRIBUTING.md`.
The study agent never reads `docs/`.

## Status (2026-10-19)

- Content: 49 topics (46 from the course workbooks + 3 `gen`), 313 questions (293 workbook + 20 general),
  140 project cards. Built once for the FullStack 2026 cohort, and **won't be updated for that cohort**.
  A future round with a different curriculum starts from scratch: reuse the method, not the content.
- Review: the mentor is reviewing the rubrics. Topic and card headers say "flagged items reviewed by the mentor,
  full review in progress", and the `standalone/` headers say "draft, mentor review pending". When the review
  is done, update **both** to the same wording.
- Students get the repo through git and use it with **Claude Code or Codex**. Students without either use `standalone/`.

## Students use Windows → skills exist twice (no symlinks)

Almost every student uses **Windows**. Symlinks committed to git often arrive as plain text files there
(depending on the git settings), and then the agent finds no skills. So **there is no symlink**: the skills are
**two identical copies**:

| Path | Read by | Invocation |
|---|---|---|
| `.agents/skills/<name>/SKILL.md` | Codex | `$name`, or `/skills` |
| `.claude/skills/<name>/SKILL.md` | Claude Code | `/name` |

- **`.agents/skills/` is the source.** Edit it, then copy it over `.claude/skills/` and check that they match:
  `diff -r .agents/skills .claude/skills` (Git Bash / WSL) must print nothing.
- Both use the open Agent Skills format: `SKILL.md` with `name` and `description` frontmatter. Write the
  skill body without tool-specific syntax: refer to other skills by name (`mentor`), not as `/mentor`.
- Keep the skill name `prep`; don't rename it to `plan`. Claude Code has a built-in plan mode, and a `plan`
  skill could clash with it.

## Instructions: one file, read by both agents

- `AGENTS.md` holds all agent instructions. Codex reads it directly.
- `CLAUDE.md` only contains `@AGENTS.md` (Claude Code's import syntax). No symlink, so it works on Windows.
- Codex only reads up to 32 KiB of `AGENTS.md` by default. It is ~6 KB now; keep it small, since both agents
  load it every session.
- Links checked on 2026-10-19:
  - Codex AGENTS.md: https://learn.chatgpt.com/docs/agent-configuration/agents-md
  - Codex skills: https://learn.chatgpt.com/docs/build-skills

## Content invariants (check after every change)

- **Topic ids** are identical in `questions/index.yaml`, `progress/topics.yaml` and `curriculum/INDEX.md`.
- In `questions/index.yaml`, `count` and `ids` match the topic file.
- **Question ids** (`PB-FN-05`, `GEN-JS-01`, …) are unique and never renumbered. Append new ones.
- **Links between rubrics and cards:** `Practised in` on a rubric, `Related questions` on a card, and the topic
  line in `curriculum/INDEX.md` must agree. There is no generator in this repo, so keep them in sync by hand.
- **Card titles** match the real project titles in the course. One quirk: the Web project titled just "Use"
  really has that title. Two projects named *Secure ERP* exist, one in m1 and one in m3; they're different
  projects.
- **Size:** hand-written files ~150 lines. Rubric and card files may reach ~250 lines because of their fixed
  structure (the largest is ~236).
- **Workbook topics** (`source: workbook`) hold the course's own questions. New questions go into `gen` or a
  new topic marked "general, not course-reviewed".

## Scenarios (interview formats)

- `scenarios/<name>.md` describes how one interview runs; `progress/profile.yaml` `scenario` selects it.
  Structure: `scenarios/README.md`. The skills `interview` (modes `rehearsal`, `warmup`, `theory`,
  `devops-task`) and `prep` read it; `progress` reports `rehearsals` from `plan.yaml`.
- **`fullstack-2026-trial` is cohort-specific** (the FullStack 2026 group's trial interview, described by
  the mentor on 2026-10-20) and is the default in `profile.yaml`. For later groups: write `general.md`
  (now a placeholder) and change the default in `profile.yaml` to `general`. Keep the cohort file as an example.
- `fullstack-2026-trial-tasks.md` holds practice variants for the DevOps practical. T1 is the mentor's own
  example; the rest were drafted by the agent and should be checked by the mentor. None may be a course project.
  Checked on 2026-10-20 against the raw course text in `journey-skills`: no shared 6-word runs. Three drafts
  were reshaped so they don't mirror a project: B1 (not the GitHub Actions CI Project's shape), D3 (not the
  Pet Shop frontend), T3 (not the VPC build of Networking in the Cloud 1).
- Defaults chosen for the rehearsal (change them in the scenario file):
  - Theory budget: 11 questions (2 each from m1–m3 with one follow-up, 5 DevOps with 2–3).
  - Scoring 1 / 0.5 / 0; mapped to topic scores 1 → 3, 0.5 → 2, 0 → 1 (in the `interview` skill).
  - Language: Hungarian with one theory question in English (mentor, 2026-10-21); `interview_language: hu` in the profile.
  - Warm-up: a real 6–7 kyu kata on codewars.com (its tests decide); offline fallback: an agent-invented kata
    with 3 visible and 3 "hidden" cases the student runs. No test files written by the agent (tokens).
  - Practical: the student runs it and shows it works (the real interview expects this). The agent never
    writes, edits or runs the student's files and gives no reference solution. `terraform apply` only in the
    student's own AWS account with free resources, then `destroy`; the agent never handles credentials or state.
  - Timing: budgets only; the student runs their own timer (agents can't track wall-clock time reliably).
- Scenario files are student-visible like everything else: no internal score sheets or pass thresholds.
- The scenario and its tasks file are also copied to `standalone/` (identical copies; keep them in sync).

## Two copies of the content: `standalone/`

- `standalone/` holds the same rubrics and cards as 12 combined files (`<PREFIX>-projects / -questions /
  -index.md`) plus `instructions.md`, for Claude Projects and ChatGPT. Limits there: instruction field
  ≤ 8000 characters (now ~6.9k), ≤ 20 knowledge files (now 14 plus the instructions).
- It has no progress tracking and no `gen` topics. It has the scenario files (same names) and a rehearsal mode (Mode 5).
- When you change a rubric, a card or a scenario file, change it in **both** places. With no planned updates this is rare,
  but there's no automation.

## Where the content came from

- The content was built in the mentor's separate tooling repo, `journey-skills`, in its `interview-prep/`
  folder. That repo had read access to the course platform and to the curriculum repo.
- The questions are verbatim from each module's Tech Interview Workbook. Cards and rubrics were written for
  this repo at concept level.
- An **IP leak check** compared every line with the raw course text. It flagged shared 6-word runs and
  shared code spans. It **only runs in `journey-skills`**, because it needs the raw course dump, which must
  never be copied here.
- If you change cards or rubrics substantially, copy them back there and re-run
  `scripts/interview-prep-check.py`, or have someone with access do it. For small edits, follow the rules
  in `CONTRIBUTING.md`.
- Pre-merge backup of this repo, from before the content was merged in:
  `~/work/interview-assistant-pre-merge-2026-10-19.tar.gz`. It can be deleted once this repo is under git.

## Known source issues (from the workbooks; not fixed upstream)

- **OOP-TEST-04:** the Java workbook asks about NUnit (.NET). The course expected JUnit. A "Note for the
  agent" makes the agent accept both and ask for JUnit.
- **DevOps workbook:** it has no CI/CD questions, although week 6 is CI/CD. `gen-devops` fills the gap.
- **Programming Basics workbook:** two questions in "Data Basics" were merged into one line. The bank splits
  them into PB-DATA-01 and PB-DATA-02.
- **Facts that changed since the workbooks were written:** handled with "Note for the agent" lines in
  WEB-REACT-02 / 04 / 13, WEB-LANG-08 and DEVOPS-SEC-03. WEB-REACT-09 (`defaultProps`) and PB-FN-03
  (call by sharing) were corrected in the rubric text itself.
