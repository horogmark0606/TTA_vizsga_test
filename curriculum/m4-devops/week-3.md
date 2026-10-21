# Advanced – DevOps — Networking and AWS core

> Project cards for Week 3 — Networking and AWS core. Concept level only: no project descriptions,
> tasks or solutions. Question IDs point to topics in `questions/index.yaml`.
> Status: drafted 2026-10-19; mentor review in progress.

## Week 3 — Networking and AWS core

### DEVOPS · AWS touchdown (solo, week 3)

**Concepts to understand**
- Cloud computing basics; the free tier and budget alerts.
- EC2 instances, instance types, AMIs.
- Security groups that allow SSH only from your own IP.
- Connecting with SSH; copying files with `scp`.
- Terminating resources to avoid costs.

**Typical pitfalls**
- SSH open to the whole internet.
- Forgotten running instances.

**Explain-your-own-code prompts**
- "Who is allowed to SSH into your instance, and where is that decided?"
- "What protects you from a surprise bill?"

**Related questions:** DEVOPS-NET-14, DEVOPS-SEC-04, DEVOPS-LINUX-01

### DEVOPS · AWS API (team, week 3)

**Concepts to understand**
- Not using the root account for daily work; an admin IAM user instead.
- Installing and configuring the AWS CLI.
- S3: buckets and objects, from the console and from the CLI.
- Sharing a private object safely with a presigned URL.
- Public vs. private buckets.

**Typical pitfalls**
- Access keys committed or shared.
- Making a bucket public to "just make it work".

**Explain-your-own-code prompts**
- "How can someone open a private file through your presigned URL, and for how long?"
- "Which credentials does your CLI use, and where are they stored?"

**Related questions:** DEVOPS-SEC-07, DEVOPS-SEC-08, DEVOPS-SEC-09

### DEVOPS · Networking in the Cloud 1 (solo, week 3)

**Concepts to understand**
- The default VPC and what AWS creates for you.
- Creating a VPC with a CIDR block.
- Public vs. private subnets.
- An internet gateway.
- Route tables and the default route.

**Typical pitfalls**
- Thinking a subnet is "public" because of its name (it's the route that decides).

**Explain-your-own-code prompts**
- "What exactly makes your public subnet public?"
- "How many addresses does your subnet have, and how many can you use?"

**Related questions:** DEVOPS-NET-10, DEVOPS-NET-11, DEVOPS-NET-14
