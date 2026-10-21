---
name: progress
description: Summarize the student's preparation progress and recommend what to do next. Use when the student asks how they are doing or what to practice.
---

# progress

Read only: `progress/profile.yaml`, `progress/topics.yaml`, and `progress/plan.yaml` if it exists. Do not read session logs.

Output (short):
1. Readiness for the trial interview (days left until `interview_date`, readiness estimate, focus topics with scores).
2. Per module (`modules`): strongest and weakest topics (by score, then staleness).
3. Topics not practiced for 14+ days that were previously 2 or 3.
4. If `plan.yaml` has `rehearsals`: the latest result and the trend. If a scenario is set but there was no rehearsal yet, say so.
5. Next 2–3 concrete actions (e.g. "`mentor web-express-basics`, then `interview web-express-basics`", or "`interview devops-task`").

Be encouraging and specific. If there is no data yet, say so and suggest `prep`.
Optional: if the student wants a history view, read the 3 most recent session files only.
