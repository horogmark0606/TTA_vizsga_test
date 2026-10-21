---
name: extend
description: Extend this repo - add a topic, interview questions, a curriculum link, or a new practice method (later also HR/behavioral questions). Use when the student wants to improve or customize the project.
---

# extend [topic | questions | curriculum | method | scenario | module]

Read `docs/CONTRIBUTING.md` first (it holds the file formats and the content rules). Then, by type:

- **questions:** open the target topic file, append rubrics in the same format with the next free id. Update `count` and `ids` in `questions/index.yaml`. New questions the student adds go into a `gen` topic (or a new one) and are marked "general, not course-reviewed", never into a workbook topic.
- **topic:** create `questions/<module>/<topic-id>.md` from the format, add it to `questions/index.yaml`, add `<topic-id>` to `progress/topics.yaml` (score 0), add a line in `curriculum/INDEX.md`.
- **curriculum:** add the project to `curriculum/INDEX.md` or a card to the right week file. Concept level only: never paste project descriptions, task wording, starter or reference code.
- **method:** create `methods/<name>.md` (when to use, steps for the agent, what to persist) and add a row to `methods/README.md`. Skills may reference it by name.
- **scenario** (how an interview runs): create `scenarios/<name>.md` with the structure in `scenarios/README.md` (and `<name>-tasks.md` for practice tasks), add a row to that README. The student selects it with `scenario` in `progress/profile.yaml`.
- **module** (e.g. `hr-behavioral`): new folder under `questions/`, same index/progress/curriculum updates; add the module to the header of `questions/index.yaml`.

Keep everything small and consistent with the ids and scoring in `AGENTS.md`. Ask the student for the content or help them draft it. Check the quality of questions: clear, one key idea, rubric points written as terse keywords, never as a model answer.
