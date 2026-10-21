# Interview Assistant

Prepare for the trial tech interview at the end of the course with an AI mentor and mock interviewer.
Built for Codecool FullStack students, extendable by you. Works with **Claude Code** and **Codex**.

The question bank holds the interview questions of the four course modules (from the Tech Interview
Workbooks), each with a checklist the agent uses to give feedback. **It never gives you a model answer**:
it asks, probes, points you back to the project where you practised the topic, and lets you find the answer yourself.

## Getting started

1. On GitHub, click **Use this template → Create a new repository**, choose **your own account** and set it
   to **Private** (your progress will be saved there). Then clone your new repo.
   No GitHub account? Download the ZIP and use it locally.
2. Open the folder with your agent: `claude` (Claude Code) or `codex` (Codex).
3. Edit `progress/profile.yaml`: interview date, interview language, how much help you want, which modules.
   `scenario` says how your interview runs (FullStack 2026 group: already set, see `scenarios/`).
4. Run the `prep` skill to plan until the interview.
5. Use `mentor` to learn, `interview` to practise, `progress` to see where you stand.
   Rehearse your interview's format: `/interview rehearsal` (Codex: `$interview rehearsal`) runs the whole
   ~90 minutes; `/interview warmup`, `/interview theory` or `/interview devops-task` practises one section.
   Want feedback on your own workbook answer, or practice explaining a project? Just ask: the agent uses the
   **check-my-answer** and **explain-my-project** methods.

How to run a skill:

| | Claude Code | Codex |
|---|---|---|
| Run a skill | `/prep`, `/interview`, `/mentor`, … | `$prep`, `$interview`, `$mentor`, … (or `/skills`) |
| Or just say it | "let's do a mock interview on React" | same |

No Claude Code or Codex? See `standalone/README.md` for a version you can upload to a Claude Project or ChatGPT.

## What is inside

| Path | What |
|---|---|
| `AGENTS.md` | Agent instructions, token-saving rules, the rules about answers and course content (`CLAUDE.md` imports it) |
| `.agents/skills/`, `.claude/skills/` | The skills: prep, mentor, interview, progress, extend (same content twice: Codex reads the first, Claude Code the second) |
| `questions/` | Interview question bank with rubrics, one file per topic, indexed in `index.yaml` |
| `curriculum/` | Project cards: what each course project should have taught you, by module and week |
| `scenarios/` | How your interview runs (sections, time budgets, scoring) and practice tasks for its practical parts |
| `methods/` | Practice methods (check my answer, explain my project, teach-back, ...). Add your own |
| `progress/` | Your profile, plan, scores and session logs (this is yours) |
| `standalone/` | Upload version for Claude Projects / ChatGPT |
| `docs/` | How to extend and maintain the repo, and why it works the way it does |

## Make it yours

This is your repo. Add questions, topics, and practice methods with the `extend` skill.
Questions you add are marked "general, not course-reviewed" so they stay separate from the course's own.
Later, HR/behavioral interview prep can be added as a new module under `questions/` and a new method under `methods/`.

## Privacy

`progress/` contains your personal data. Keep your copy private.
