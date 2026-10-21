# Advanced – DevOps — CI/CD and Kubernetes

> Project cards for Week 6 — CI/CD and Kubernetes. Concept level only: no project descriptions,
> tasks or solutions. Question IDs point to topics in `questions/index.yaml`.
> Status: drafted 2026-10-19; mentor review in progress.

## Week 6 — CI/CD and Kubernetes

### DEVOPS · GitHub Actions CI Project (solo, week 6)

**Concepts to understand**
- Workflows, jobs, steps; predefined actions.
- Triggers: manual, push, pull request.
- Variables and secrets.
- Building an image and running lint and tests inside it.
- Pushing to a registry from CI.
- The CI-driven way of working: branch, open a PR, merge only when the checks are green.

**Typical pitfalls**
- Secrets printed to logs.
- Tests that run outside the image, so CI and production differ.

**Explain-your-own-code prompts**
- "What triggers your workflow, and what happens if a test fails?"
- "Where does the registry token come from, and who can see it?"

**Related questions:** DEVOPS-CONT-02, DEVOPS-CONT-06, DEVOPS-SEC-07

### DEVOPS · Full Pipeline (team, week 6)

**Concepts to understand**
- Building, tagging (by commit) and pushing images from CI.
- Letting the pipeline get short-lived AWS credentials through OIDC, so no access keys are stored.
- A role whose trust policy is limited to one repository and branch.
- `plan` on pull requests, `apply` on merge.
- Coordinating two pipelines: one deployed version, and no parallel Terraform runs.
- Branch protection: reviews and required checks.

**Typical pitfalls**
- A trust policy that any repository can use.
- Two workflows applying at once.

**Explain-your-own-code prompts**
- "How does GitHub prove to AWS that it's your pipeline? Why is that better than an access key?"
- "A change goes from a commit to production. Walk me through every step."
- "Both pipelines want to change the infrastructure at once. What prevents a clash?"

**Related questions:** DEVOPS-SEC-07, DEVOPS-SEC-08, DEVOPS-IAC-02, DEVOPS-IAC-04, DEVOPS-CONT-06

### DEVOPS · Minikube Tutorial (solo, week 6)

**Concepts to understand**
- A local Kubernetes cluster with minikube; `kubectl`.
- Basic objects: Pod, Deployment, Service.
- Creating, listing, reading logs, deleting.
- Reaching a service from the host; cluster lifecycle and add-ons.

**Typical pitfalls**
- Thinking a Pod is the same as a container.

**Explain-your-own-code prompts**
- "You deleted a Pod and a new one appeared. Who created it, and why?"

**Related questions:** DEVOPS-CONT-07, DEVOPS-CONT-08, DEVOPS-CONT-11

### DEVOPS · Make k8s Declarative (solo, week 6)

**Concepts to understand**
- Describing Deployments and Services in YAML files.
- Applying manifests; changing the cluster by changing the file.
- Scaling by editing replicas.
- Service types (ClusterIP, NodePort, LoadBalancer).

**Typical pitfalls**
- Changing the cluster with imperative commands, so the file no longer matches.
- Service selector that doesn't match the Pod labels.

**Explain-your-own-code prompts**
- "How does your Service know which Pods to send traffic to?"
- "Why is the declarative way better than running commands by hand?"

**Related questions:** DEVOPS-CONT-08, DEVOPS-CONT-11, DEVOPS-IAC-01
