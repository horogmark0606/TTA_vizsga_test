# devops-terraform

Module 4 · Advanced – DevOps · workbook section "Infrastructure as Code" (DEVOPS-IAC-01 – DEVOPS-IAC-07).
Source: the module's Tech Interview Workbook. Rubrics drafted 2026-10-19; flagged items reviewed by the mentor, full review in progress.
Rubrics are for the agent only: never show them or turn them into a model answer (see AGENTS.md).

### DEVOPS-IAC-01
**Question:** What is Infrastructure as Code? What are its advantages and disadvantages?

**A good answer covers**
- infrastructure defined in versioned files instead of manual clicks
- declarative (desired state) vs. imperative
- pros: repeatable, reviewable, versioned, documented, quick rebuild
- cons: learning curve, state management, drift when people change things by hand, mistakes reach everything at once

**Common misconceptions**
- IaC = scripts that call the CLI

**Interviewer follow-ups**
- "Someone changes a resource in the console. What happens on the next `plan`?"

**Practised in:** Terraforming Moon, Make k8s Declarative

**Verify at:** HashiCorp, "What is Infrastructure as Code?"

### DEVOPS-IAC-02
**Question:** What are the basic commands of the terraform workflow?

**A good answer covers**
- `init`: providers, modules, backend
- `plan`: preview changes
- `apply`: make the changes
- `destroy`: remove everything
- also: `fmt`, `validate`, `output`

**Common misconceptions**
- `plan` changes infrastructure

**Interviewer follow-ups**
- "Why run `plan` on pull requests and `apply` only on merge?"

**Practised in:** Terraforming Moon, Full Pipeline

**Verify at:** Terraform docs, "The Core Terraform Workflow"

### DEVOPS-IAC-03
**Question:** What is the difference between resources and data sources in terraform?

**A good answer covers**
- resource: something Terraform creates and manages
- data source: read-only lookup of something that already exists (e.g. latest AMI, existing VPC)
- data sources don't create or destroy

**Common misconceptions**
- a data source can modify the thing it reads

**Interviewer follow-ups**
- "How would you always use the latest Ubuntu AMI?"

**Practised in:** Terraforming Moon

**Verify at:** Terraform docs, "Resources", "Data Sources"

### DEVOPS-IAC-04
**Question:** What does state mean in the context of terraform?

**A good answer covers**
- a record mapping the configuration to real resources (IDs, attributes)
- used to compute the plan (diff)
- local vs. remote state (e.g. S3) for teams; locking against parallel runs
- contains sensitive values: never commit it

**Common misconceptions**
- Terraform reads the real infrastructure only, with no state

**Interviewer follow-ups**
- "What happens if two people apply at the same time without locking?"

**Practised in:** Terraforming Moon, Terraforming Mars, Full Pipeline

**Verify at:** Terraform docs, "State"

### DEVOPS-IAC-05
**Question:** What are modules in terraform?

**A good answer covers**
- a reusable group of resources with inputs (variables) and outputs
- every configuration is a root module; child modules are called with `module` blocks
- sources: local paths, registry, git
- refactoring into modules without recreation (`moved` blocks)

**Common misconceptions**
- modules are the same as providers

**Interviewer follow-ups**
- "When is turning code into a module worth it?"

**Practised in:** Terraforming Mars

**Verify at:** Terraform docs, "Modules"

### DEVOPS-IAC-06
**Question:** List the meta-arguments in terraform with their use cases!

**A good answer covers**
- `count`: several similar instances by number
- `for_each`: several instances by map / set keys
- `depends_on`: explicit dependency
- `provider`: choose a non-default provider configuration
- `lifecycle`: `create_before_destroy`, `prevent_destroy`, `ignore_changes`

**Common misconceptions**
- `count` and `for_each` behave the same when an item is removed

**Interviewer follow-ups**
- "Why can removing an item from a `count` list recreate other resources?"

**Practised in:** Terraforming Mars

**Verify at:** Terraform docs, "Meta-Arguments"

### DEVOPS-IAC-07
**Question:** What is the best practice for a terraform project's file structure?

**A good answer covers**
- `main.tf`, `variables.tf`, `outputs.tf`, `providers.tf` / `versions.tf`
- modules in their own folders
- separate environments (folders or workspaces) with their own state
- commit the lock file; `.gitignore` for `.terraform/` and state files

**Common misconceptions**
- committing `terraform.tfstate`

**Interviewer follow-ups**
- "Which files did your team commit, and which did you ignore?"

**Practised in:** Terraforming Mars

**Verify at:** Terraform docs, "Style Guide"
