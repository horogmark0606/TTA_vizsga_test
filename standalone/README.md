# Standalone version (no Claude Code)

For a Claude Project or ChatGPT (custom GPT or Project), if you don't use Claude Code.
Same content as the repo, in fewer, bigger files. No progress tracking.

## Install

- **Claude Project:** paste `instructions.md` into the project instructions, then upload the 3 files of the
  module you're preparing for as project knowledge.
- **ChatGPT:** paste `instructions.md` into Instructions, then upload the 3 files of the module as Knowledge.

The 3 files per module (`PB` Programming Basics, `WEB` Web Frameworks, `OOP` OOP with Java, `DEVOPS` Advanced – DevOps):
`<PREFIX>-projects.md`, `<PREFIX>-questions.md`, `<PREFIX>-index.md`.

**One module at a time.** One module is roughly 14–25k tokens; all four together are about 75k. Depending on the
platform, a bigger knowledge base may cost more tokens per message, and it makes the agent less focused.
Swap the files when you move on to the next module.

**Rehearsing the trial interview (FullStack 2026 group):** upload `fullstack-2026-trial.md`,
`fullstack-2026-trial-tasks.md` and the four `<PREFIX>-questions.md` files (about 45k tokens), and choose mode 5.
For one section only (e.g. the DevOps practical), the two scenario files and `DEVOPS-questions.md` are enough.

The general extras (`gen` topics) are only in the Claude Code version.
