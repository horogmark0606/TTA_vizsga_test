---
name: prep
description: Plan the preparation for the trial tech interview at the end of the course - set the date, find weak modules and topics, and create a day-by-day focus plan. Use when the student starts preparing or wants a new plan.
---

# prep

Goal: create or update `progress/plan.yaml` (from `progress/plan_template.yaml` if it doesn't exist yet).

Steps:
1. Read `progress/profile.yaml`. Ask the student, one at a time (skip what is already known):
   interview date (store it as `interview_date` in `profile.yaml`), which modules feel weakest, how much time they have per day.
2. If `scenario` is set (not `null`): read `scenarios/<scenario>.md` (not the tasks file). Plan for its sections, not only for questions.
3. Read `questions/index.yaml` (topics of the modules in `profile.yaml` `modules`). Do not open topic files yet.
4. Read `progress/topics.yaml`. Rank: topics of the weak modules with the lowest scores first, then stale topics.
5. Fill `progress/plan.yaml`: `focus_topics` (max 8, ordered), `plan` (short next steps).
6. Propose a short plan (what to do each day until the date) in 5–8 lines. Ask if it fits their time.
7. Suggest the first `mentor` or `interview` step.

Spread the plan over all four modules unless the student narrowed `modules`: the trial interview covers the whole course.

With a scenario, weight the plan the way the scenario does. For `fullstack-2026-trial`:
- DevOps (m4) in depth: about half of the theory practice, with follow-ups; m1–m3 still every few days.
- A short warm-up kata most days (`interview warmup`, or 6–7 kyu katas on codewars.com in their language).
- Each practical type at least once (Dockerfile, image build, Terraform) with `interview devops-task`.
- One full `interview rehearsal` around the middle and one 2–3 days before the date. Not more: it is long and costs tokens.
