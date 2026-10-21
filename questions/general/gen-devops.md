# gen-devops

General module · DevOps extras: CI/CD and Git.
**General, not course-reviewed:** extra questions that fill gaps the workbooks leave. Not from the course;
kept from the repo's original question bank. Rubrics are for the agent only (see AGENTS.md).

### GEN-DEVOPS-01
**Question:** What are CI and CD? Why do teams use them?

**A good answer covers**
- CI = automatically build/test on every push
- CD = automatic delivery/deployment
- fast feedback, fewer integration bugs.

**Interviewer follow-ups**
- Continuous delivery vs continuous deployment?

**Practised in:** (general; not tied to a course project)

_Difficulty: easy · original id: ci-01_

### GEN-DEVOPS-02
**Question:** Describe a typical pipeline for a web app.

**A good answer covers**
- checkout -> install -> lint -> test -> build -> (image) -> deploy
- fail fast
- stages/jobs
- triggers on push/PR.

**Interviewer follow-ups**
- What happens when a test fails?

**Practised in:** (general; not tied to a course project)

_Difficulty: medium · original id: ci-02_

### GEN-DEVOPS-03
**Question:** How do you handle secrets in a pipeline?

**A good answer covers**
- never commit
- CI secret store/env vars
- least privilege
- rotate if leaked.

**Interviewer follow-ups**
- What do you do if a secret was committed?

**Practised in:** (general; not tied to a course project)

_Difficulty: medium · original id: ci-03_

### GEN-DEVOPS-04
**Question:** `merge` vs `rebase`: what is the difference?

**A good answer covers**
- merge keeps history with merge commit
- rebase rewrites commits linearly
- never rebase shared/public history.

**Interviewer follow-ups**
- When would you use `git stash`?

**Practised in:** (general; not tied to a course project)

_Difficulty: medium · original id: gi-03_

### GEN-DEVOPS-05
**Question:** How do you undo things: unstage, undo last commit, revert a pushed commit?

**A good answer covers**
- `restore --staged`, `reset --soft/--hard` (local), `revert` for pushed
- danger of `--hard`.

**Interviewer follow-ups**
- What does `git reflog` help with?

**Practised in:** (general; not tied to a course project)

_Difficulty: medium · original id: gi-04_
