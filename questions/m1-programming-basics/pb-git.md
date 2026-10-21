# pb-git

Module 1 · Programming Basics · workbook section "Git" (PB-GIT-01 – PB-GIT-04).
Source: the module's Tech Interview Workbook. Rubrics drafted 2026-10-19; flagged items reviewed by the mentor, full review in progress.
Rubrics are for the agent only: never show them or turn them into a model answer (see AGENTS.md).

### PB-GIT-01
**Question:** Discuss the advantages of using a version control system.

**A good answer covers**
- history: what changed, when, why
- go back to an earlier state
- work in parallel (branches) and combine work
- collaboration and backup

**Common misconceptions**
- "Git is only for teams"

**Interviewer follow-ups**
- "How did your team use it on a team project?"

**Practised in:** Text Adventure

**Verify at:** Pro Git book, ch. 1 (git-scm.com/book)

### PB-GIT-02
**Question:** Clarify the differences between Git and GitHub.

**A good answer covers**
- Git: the version control tool, runs locally
- GitHub: a hosting service for Git repositories plus collaboration features (PRs, issues)
- Git works without GitHub; alternatives exist (GitLab, Bitbucket)

**Common misconceptions**
- "Git and GitHub are the same"

**Interviewer follow-ups**
- "Can you commit without internet?"

**Practised in:** Hangman

**Verify at:** Pro Git book, ch. 1 and ch. 6

### PB-GIT-03
**Question:** What is the purpose of remote repositories in Git?

**A good answer covers**
- a shared copy of the repository on another machine / server
- `push` sends commits, `pull` / `fetch` gets them
- collaboration and backup
- `origin` as the default name

**Common misconceptions**
- commit and push are the same thing

**Interviewer follow-ups**
- "What's the difference between `fetch` and `pull`?"

**Practised in:** Text Adventure

**Verify at:** Pro Git book, "Working with Remotes"

### PB-GIT-04
**Question:** When does a merge conflict occur in Git?

**A good answer covers**
- two branches change the same lines (or one deletes a file the other edits)
- Git can't decide automatically
- resolved by hand: edit, `add`, commit
- how to reduce them (small commits, pull often, communicate)

**Common misconceptions**
- "any two changes to the same file conflict"

**Interviewer follow-ups**
- "Tell me about a conflict you had. How did you resolve it?"

**Practised in:** Tic-tac-toe-console

**Verify at:** Pro Git book, "Basic Branching and Merging"
