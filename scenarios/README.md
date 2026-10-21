# Scenarios: how the interview runs

A scenario describes the format of one interview (sections, time budgets, scoring), so the agent can rehearse
exactly that. The questions and rubrics stay in `questions/`; a scenario only says how they are used.

Pick one in `progress/profile.yaml` with `scenario: <file name without .md>`. Empty (`null`) means no
scenario: the agent runs topic-based mock interviews.

| Scenario | For |
|---|---|
| `fullstack-2026-trial` | The FullStack 2026 group's trial tech interview (practice tasks in `fullstack-2026-trial-tasks.md`) |
| `general` | A general tech interview (placeholder, not written yet) |

Use it with the `interview` skill: `rehearsal` runs the whole interview, or practise one section
(e.g. `warmup`, `theory`, `devops-task`). The `prep` skill plans around the scenario.

## Structure of a scenario file

1. **Format:** who interviews, how long, online or not, what is not part of it.
2. **Sections:** a table with time budgets, in order.
3. **Scoring:** what earns full, partial and no points.
4. **Rehearsal: rules for the agent:** one subsection per section (what to ask, budgets, what not to do).
5. **Debrief:** what the feedback covers.

Practice tasks go into a separate `<scenario>-tasks.md`, so the agent loads them only when needed.
Everything here is student-visible: no internal score sheets or pass thresholds unless they may be shared.
