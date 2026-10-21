# Advanced – DevOps — Terraform deploys the Compose stack

> Project cards for Week 5 — Terraform deploys the Compose stack. Concept level only: no project descriptions,
> tasks or solutions. Question IDs point to topics in `questions/index.yaml`.
> Status: drafted 2026-10-19; mentor review in progress.

## Week 5 — Terraform deploys the Compose stack

### DEVOPS · Terraforming Mars (team, week 5)

**Concepts to understand**
- Remote state in S3 with locking, for a team sharing one infrastructure.
- A VPC across availability zones; public and private subnets.
- Shipping a Compose stack to EC2: images from a registry, start-up through user data.
- A managed database that the internet can't reach; only the app's security group may connect.
- A fixed public address.
- Turning working code into a module; refactoring without recreating resources.
- Rebuilding everything from code; documenting the architecture.

**Typical pitfalls**
- State file committed to git.
- Images built for the wrong CPU architecture.
- A refactor that destroys and recreates the database.

**Explain-your-own-code prompts**
- "Two of you run `apply` at the same time. What stops you from corrupting the state?"
- "How does the app learn the database address?"
- "You moved resources into a module. Why didn't Terraform recreate them?"

**Related questions:** DEVOPS-IAC-04, DEVOPS-IAC-05, DEVOPS-IAC-06, DEVOPS-IAC-07, DEVOPS-CONT-06, DEVOPS-SEC-04
