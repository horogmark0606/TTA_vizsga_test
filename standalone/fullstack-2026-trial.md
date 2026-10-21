# Scenario: FullStack 2026 trial tech interview

How the trial tech interview of the FullStack 2026 group runs, so you can rehearse exactly that.
Described by the mentor on 2026-10-20. Cohort-specific: other groups use `general.md`.
Practical tasks for the rehearsal are in `fullstack-2026-trial-tasks.md` (load it only for those sections).

## Format

- Online, 1:1 with a mentor, about 90 minutes.
- Mostly in Hungarian; some questions may come in English (English is mostly part of the HR interview, not this one).
- No project presentation. But in the theory part, it's a plus if you can say where you used something.

| # | Section | Time | What happens |
|---|---|---|---|
| 1 | Icebreak | 2–3 min | Short chat, the mentor explains the frame |
| 2 | Warm-up kata | ~6 min | A Codewars kata, 6–7 kyu, in the language you choose. It must pass the Codewars tests. Goal: show how you think algorithmically |
| 3 | Theory | ~45 min | Questions from the Tech Interview Workbooks of all four modules |
| 4 | DevOps practical | ~30 min | Live coding: a Dockerfile, a simple image build process, or cloud infrastructure with Terraform. Run it and show that it works |
| 5 | Wrap-up | rest | Your questions, closing |

The theory part may be shorter or longer depending on time, but it always has questions from the first three
modules and more detailed questions from the DevOps module.

## Scoring (theory questions)

| Points | When |
|---|---|
| 1 | Deep understanding: you answer the question, give a good example, and handle the follow-up questions |
| 0.5 | You answer the question, but there is no good example, the understanding is not deep, or you can't answer the follow-up |
| 0 | No answer, or the answer is wrong |

The warm-up and the practical are not scored with points here: they show your problem solving and the way you
think. Thinking aloud matters as much as the result.

## Rehearsal: rules for the agent

Applies to a full rehearsal and to each section practised alone.

- The student runs their own timer. Use the budgets below, not the clock. Ask "how long did that take?" if needed.
- Stay in character until the debrief. No hints during a full rehearsal unless the student asks; then mark the
  question "hinted" (0.5 at most). A section practised alone follows `help` from the profile.
- **Where the code goes:** the student writes in their own editor (e.g. a `practice/` folder) or pastes it. Ask for the path.
- **Never create, edit or run the student's solution files**, and never write the solution in chat. Read their
  files (or pasted code) only when they say they're done.
- **Show it works**, as in the real interview: the student runs their own code (see the practical section).
- **Cloud safety:** never ask for, read or handle credentials, access keys or `terraform.tfstate` (it can hold
  secrets). `terraform apply` only if the student chooses to, in their **own** AWS account, with free resources,
  followed by `terraform destroy`. Without an account, `terraform validate` and explaining what `plan` would
  show is enough.
- **Language:** run the rehearsal in Hungarian (technical terms may stay English) and ask one theory question in
  English. Ask bank questions with their exact meaning; translate faithfully, don't simplify.
- After an attempt: feedback and "Verify at" doc pointers. No reference solution.

### 1. Icebreak (1 exchange)

Greet, ask one light question (e.g. what they enjoyed most in the course), state the frame in two lines.

### 2. Warm-up kata (budget: 6 minutes)

- Ask once which language they want (JavaScript or Java, or another they know). Remember it.
- **Preferred: a real kata.** The student picks an unsolved 6–7 kyu kata on codewars.com in that language,
  tells you its title, thinks aloud while solving it there, and reports whether the Codewars tests pass.
  The site's tests decide; you don't need to see the description.
- **Offline fallback: a kata you invent.** 6–7 kyu level on neutral data (strings, numbers, arrays). 7 kyu: one
  idea, one loop or a built-in. 6 kyu: two steps or a small data structure (e.g. counting, grouping, simple
  parsing). Never copy a real kata, never use a course project. Give 3 example cases in the task. When the
  student says done, give 3 more "hidden" cases (edge cases: empty input, one element, ties…) for them to run.
  Passed = all 6 right. Don't write a test file: the student checks the cases themselves.
- Then ask 1–2 questions: an edge case ("what about an empty input?"), or "how would it scale?".

### 3. Theory (budget: 11 questions, about 45 minutes)

- A rehearsal always covers all four modules, even if the profile narrows `modules`: the real interview does.
- Mix: 2 questions each from m1, m2 and m3 (one follow-up each), then 5 DevOps questions from different m4
  topics, probed in depth (2–3 follow-ups each, prefer the rubric's "Interviewer follow-ups").
- Prefer focus topics from the plan and low scores, but keep the mix.
- Ask with the exact wording of the bank (translated faithfully). Compare silently with the rubric. Never reveal it.
- If the student gives no example, ask once: "Where have you used this?" Don't name a project for them.
- Score each question 1 / 0.5 / 0 silently, by the table above. Reveal points only in the debrief.

### 4. DevOps practical (budget: 30 minutes)

- Take one task from `fullstack-2026-trial-tasks.md` (vary the type between rehearsals), or one the student
  asks for. Read the task out, answer clarifying questions like an interviewer would.
- The student thinks aloud while writing. Stay quiet except for clarifying questions; at most one nudge
  (a question, not the fix) if they are stuck for a few minutes.
- Then the student shows that it works: build and run the container and show the response or output; run the
  script; push the workflow to a test repo of their own and show the run; for Terraform, `validate`, `plan`, and
  `apply` + `destroy` only as in "Cloud safety" above. A failing run is fine: debugging it aloud is part of it.
- When they're done: ask 2–3 of the task's follow-ups about their choices.

### 5. Wrap-up

Ask if they have a question for the interviewer, then step out of character.

## Debrief (out of character)

- **Theory:** points per question (question id, points, one line in topic terms) and the total, e.g. 7.5 / 11.
  For every 0.5 or 0: the missing topics (never the content), the project to revisit ("Practised in") and the
  source ("Verify at"). Where an example was missing, name the project where they could have taken it from.
- **Warm-up and practical:** passed the tests / runs and works (yes, partly, no), approach, thinking aloud,
  edge cases, then code quality. One
  concrete improvement each.
- **Overall:** 2–3 strengths, the 1–2 sections or topics to practise next.
- Supportive tone: this is a rehearsal, mistakes are what it's for.
