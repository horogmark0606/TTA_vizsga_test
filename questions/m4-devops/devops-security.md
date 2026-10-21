# devops-security

Module 4 · Advanced – DevOps · workbook section "Security" (DEVOPS-SEC-01 – DEVOPS-SEC-09).
Source: the module's Tech Interview Workbook. Rubrics drafted 2026-10-19; flagged items reviewed by the mentor, full review in progress.
Rubrics are for the agent only: never show them or turn them into a model answer (see AGENTS.md).

### DEVOPS-SEC-01
**Question:** What is encryption at rest and encryption in transit, and how are these implemented in AWS?

**A good answer covers**
- at rest: stored data is encrypted (disks, S3 objects, databases)
- in transit: data moving over the network is encrypted (TLS)
- AWS: KMS keys for S3 (SSE-S3 / SSE-KMS), EBS, RDS encryption
- in transit: HTTPS endpoints, TLS on load balancers (ACM certificates), enforcing TLS in bucket policies

**Common misconceptions**
- encryption at rest protects against a compromised application

**Interviewer follow-ups**
- "What does encryption at rest *not* protect you from?"

**Practised in:** Service Security

**Verify at:** AWS docs, "Data protection in Amazon S3"; AWS KMS docs

### DEVOPS-SEC-02
**Question:** Which service is responsible for monitoring and log collection in AWS?

**A good answer covers**
- Amazon CloudWatch: metrics, logs, alarms, dashboards
- (CloudTrail is for API activity, see next question)
- agents / integrations to ship logs

**Common misconceptions**
- confusing CloudWatch with CloudTrail

**Interviewer follow-ups**
- "How would you get an alert when CPU stays above 80%?"

**Practised in:** Network Security In The Cloud, Service Security

**Verify at:** AWS docs, "What is Amazon CloudWatch?"

### DEVOPS-SEC-03
**Question:** What is a bastion host, and how can it be implemented in AWS?

> Note for the agent: Changed: the old AWS "Linux Bastion Hosts" Quick Start was deprecated and archived in October 2024. If the student cites it, accept it, but mention that it's archived. The concept is unchanged. AWS now steers people towards Session Manager for shell access without open SSH.

**A good answer covers**
- a hardened jump server in a public subnet; the only SSH entry point
- private instances accept SSH only from the bastion's security group
- SSH agent forwarding / `ProxyJump` instead of copying keys
- modern alternative: Systems Manager Session Manager (no open SSH)

**Common misconceptions**
- copying the private key onto the bastion

**Interviewer follow-ups**
- "Why is Session Manager often preferred today?"

**Practised in:** Head in the Cloud 1

**Verify at:** AWS Systems Manager docs, "Session Manager"; AWS docs, "Security group rules"

### DEVOPS-SEC-04
**Question:** What are the key differences between security groups and NACLs?

**A good answer covers**
- security group: instance / ENI level, stateful, allow rules only
- NACL: subnet level, stateless (return traffic needs rules), allow and deny, numbered rule order
- security groups can reference other security groups
- used together as layers

**Common misconceptions**
- "NACLs are stateful too"

**Interviewer follow-ups**
- "How would you block a single IP address? Which one can do it?"

**Practised in:** AWS touchdown, Network Security In The Cloud, Terraforming Mars

**Verify at:** AWS docs, "Compare security groups and network ACLs"

### DEVOPS-SEC-05
**Question:** Which service is responsible for tracking activities on an AWS account?

**A good answer covers**
- AWS CloudTrail: records API calls (who, what, when, from where)
- event history (90 days) and trails to S3 for longer retention
- used for audit, security investigation, compliance

**Common misconceptions**
- CloudWatch tracks who did what

**Interviewer follow-ups**
- "A security group was opened to the world. How do you find out who did it?"

**Practised in:** Service Security

**Verify at:** AWS docs, "What is AWS CloudTrail?"

### DEVOPS-SEC-06
**Question:** Explain the difference between symmetric and asymmetric encryption!

**A good answer covers**
- symmetric: one shared key for encrypt and decrypt; fast (e.g. AES)
- asymmetric: public / private key pair; encrypt with public, decrypt with private; signatures the other way (e.g. RSA, ECC)
- key distribution problem of symmetric
- in practice combined: asymmetric to agree a key, symmetric for the data (TLS, SSH)

**Common misconceptions**
- "asymmetric is used for everything because it's more secure"

**Interviewer follow-ups**
- "Where did you use each kind in the SSH and KMS projects?"

**Practised in:** The Way to a Dev's Heart is via SSH, Service Security

**Verify at:** Cloudflare Learning, "What is asymmetric encryption?"

### DEVOPS-SEC-07
**Question:** What is the Principle of Least Privilege, and how can it be implemented in AWS?

**A good answer covers**
- give only the permissions needed, for only as long as needed
- AWS: IAM policies scoped to actions and resources; groups and roles
- no root for daily work; temporary credentials via roles
- review with IAM Access Analyzer / last-accessed data; permission boundaries

**Common misconceptions**
- "admin for everyone and restrict later"

**Interviewer follow-ups**
- "Your CI pipeline needs to deploy. How do you limit what it can do?"

**Practised in:** Linux Permissions, AWS API, AWS IAM Introduction, IAM security, GitHub Actions CI Project, Full Pipeline

**Verify at:** AWS docs, "Security best practices in IAM"

### DEVOPS-SEC-08
**Question:** How do AWS IAM roles differ from IAM users, and in what scenarios would you use each?

**A good answer covers**
- user: a long-term identity with permanent credentials (password, access keys)
- role: assumed by trusted entities (users, services, external identities); temporary credentials
- roles have a trust policy (who can assume) and permission policies (what they can do)
- use roles for EC2 / Lambda, cross-account access, CI with OIDC, admin elevation; users (or SSO) for people

**Common misconceptions**
- "a role is a group"

**Interviewer follow-ups**
- "How did your EC2 instance access S3 without keys?"

**Practised in:** AWS API, AWS IAM Introduction, IAM security, Full Pipeline

**Verify at:** AWS docs, "IAM roles"

### DEVOPS-SEC-09
**Question:** Explain the AWS Shared Responsibility Model in the context of security.

**A good answer covers**
- AWS: security *of* the cloud (hardware, facilities, hypervisor, managed service infrastructure)
- customer: security *in* the cloud (data, IAM, OS patching on EC2, network config, encryption choices)
- the split shifts with the service type (EC2 vs. RDS vs. S3)

**Common misconceptions**
- "it's in AWS, so AWS secures it"

**Interviewer follow-ups**
- "Who patches the OS on EC2? On RDS?"

**Practised in:** AWS API, IAM security, Service Security

**Verify at:** AWS, "Shared Responsibility Model"
