---
name: interview
description: Run a mock tech interview. The agent plays the interviewer, asks questions, evaluates answers, and records results. Also rehearses the whole interview of the student's scenario, or one section of it. Use when the student wants to practice or test themselves.
---

# interview [topic | module | rehearsal | <section>] [--length N]

Role: friendly but realistic interviewer. Stay in character until the debrief.

## Scenario modes

If `progress/profile.yaml` has a `scenario` (not `null`) and the student asks for `rehearsal` (the whole
interview) or one of its sections (e.g. `warmup`, `theory`, `devops-task`):
1. Read `scenarios/<scenario>.md` and follow its sections, budgets, scoring and agent rules. They override
   the defaults below (e.g. question count, number of follow-ups, no hints in a full rehearsal).
2. Load `scenarios/<scenario>-tasks.md` only when you reach a practical section.
3. Warm-up language: use `kata_language` from the profile; if it is `null`, ask and store it there.
4. Topic files: open ONE at a time, as in the default flow. Before a full rehearsal, tell the student it is
   long (and costs tokens), and that practising single sections is fine on most days.

Without a scenario, or for a topic or module: use the default flow.

## Default flow

Setup (token-efficient):
1. `progress/profile.yaml` -> `modules`, `help`, `interview_language`. Run the interview in `interview_language`.
2. If `progress/plan.yaml` exists: default to its `focus_topics`. Otherwise mix topics across `modules`.
3. `progress/topics.yaml` -> weight selection toward low scores and old `last_practiced`.
4. Open ONE topic file at a time, only when you reach that topic. Pick questions that were not asked recently (`asked` list in topics.yaml).
5. Default length: 5 questions. State the plan in one line, then start.

During the interview:
- Ask one question at a time, with the exact wording of the bank (in `hu`: a faithful translation, technical terms may stay English). The student answers from memory, workbook closed.
- Compare the answer silently against "A good answer covers". Never reveal the rubric.
- For a missing point, ask ONE probing follow-up (prefer the rubric's "Interviewer follow-ups"). Do not name the missing point. Max 2 probes per point.
- If an answer contains a rubric misconception, ask a question that makes the student test it ("What would `typeof null` print? Try it.").
- Still stuck after 2 probes: stop, mark the question "hinted", point to a project from its "Practised in" line and to its "Verify at" source. Move on.
- `help: interview-like` -> no hints unless asked; `help: more` -> offer a small hint after the first probe.
- Live coding: give a small task on unrelated data, let them write it, then ask them to explain it.
- Follow any "Note for the agent" in the rubric.

Debrief (after the last question, out of character):
- Per question: what was strong, which **topics** were missing or thin, one concrete tip. Topics only: never fill in the missing content.
- For each gap: the project to revisit ("Practised in") and the source to check ("Verify at").
- Overall: 2–3 strengths, 1–2 priorities. Supportive tone; focus on thinking, not penalties.
- Suggest the next `mentor` topic for the weakest area.
- In a scenario mode, use the scenario's debrief instead.

## Persist (required)

- `progress/topics.yaml`: update `score`, `last_practiced`, append asked ids to `asked`, add weak ids to `weak`.
  Scenario points map to topic scores: 1 -> 3, 0.5 -> 2, 0 -> 1 (several questions of one topic: take the lower).
- `progress/sessions/YYYY-MM-DD-interview.md` (or `-rehearsal.md`) from the template.
- If `progress/plan.yaml` exists: update `readiness` and `plan`. After a full rehearsal, append one line to `rehearsals`.
