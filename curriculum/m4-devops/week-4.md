# Advanced – DevOps — AWS security and Terraform basics

> Project cards for Week 4 — AWS security and Terraform basics. Concept level only: no project descriptions,
> tasks or solutions. Question IDs point to topics in `questions/index.yaml`.
> Status: drafted 2026-10-19; mentor review in progress.

## Week 4 — AWS security and Terraform basics

### DEVOPS · AWS IAM Introduction (solo, week 4)

**Concepts to understand**
- What IAM is: users, groups, policies.
- How permissions are evaluated (explicit deny, allow, default deny).
- Attaching policies to groups rather than users.
- Delegating user management to a less-privileged admin.
- Granular permissions.

**Typical pitfalls**
- Attaching policies to individual users everywhere.

**Explain-your-own-code prompts**
- "Why put the policy on a group instead of the user?"
- "An allow and a deny both match. What happens?"

**Related questions:** DEVOPS-SEC-07, DEVOPS-SEC-08

### DEVOPS · IAM security (solo, week 4)

**Concepts to understand**
- Securing the root account: MFA.
- Password policies.
- Roles and temporary credentials for users and for AWS services.
- Letting an instance access S3 through a role, without stored keys.
- Assuming a role for elevated access when needed.

**Typical pitfalls**
- Putting access keys on an EC2 instance instead of using a role.

**Explain-your-own-code prompts**
- "How does your instance get permission to read the bucket? Where are the credentials?"
- "When would you assume the admin role instead of having admin rights permanently?"

**Related questions:** DEVOPS-SEC-07, DEVOPS-SEC-08, DEVOPS-SEC-09

### DEVOPS · Network Security In The Cloud (solo, week 4)

**Concepts to understand**
- Security groups: stateful, allow-only rules, attached to resources.
- NACLs: stateless, subnet level, allow and deny, ordered rules.
- Inbound and outbound rules.
- Troubleshooting traffic (e.g. ping blocked or allowed).
- Reaching an instance without SSH through Systems Manager.

**Typical pitfalls**
- Forgetting that NACLs need return-traffic rules.

**Explain-your-own-code prompts**
- "Your ping works with the security group but stops after a NACL change. Why?"
- "How did you get a shell on the instance without opening SSH?"

**Related questions:** DEVOPS-SEC-04, DEVOPS-SEC-02, DEVOPS-NET-12

### DEVOPS · Service Security (solo, week 4)

**Concepts to understand**
- Securing S3: block public access, default encryption with your own KMS key, versioning.
- Securing EC2: restricted SSH, updated images.
- KMS: symmetric vs. asymmetric keys.
- Logging and monitoring for security (CloudTrail, CloudWatch).
- Moving fast while staying secure.

**Typical pitfalls**
- Encryption enabled, but the key policy lets everyone use the key.

**Explain-your-own-code prompts**
- "Who can decrypt the objects in your bucket? What decides that?"
- "Someone deleted an object. How do you get it back?"

**Related questions:** DEVOPS-SEC-01, DEVOPS-SEC-02, DEVOPS-SEC-05, DEVOPS-SEC-06, DEVOPS-SEC-09

### DEVOPS · Head in the Cloud 1 (team, week 4)

**Concepts to understand**
- A private subnet for resources that shouldn't be reachable from the internet.
- A bastion host as the SSH entry point.
- SSH through a jump host.
- A NAT gateway: outbound internet for private instances.
- Route tables for public vs. private subnets.

**Typical pitfalls**
- Copying the private key onto the bastion.
- A NAT gateway placed in the private subnet.

**Explain-your-own-code prompts**
- "Trace an SSH connection from your laptop to the private instance."
- "How does the private instance reach the internet, and why can't the internet reach it?"

**Related questions:** DEVOPS-SEC-03, DEVOPS-NET-14, DEVOPS-NET-10

### DEVOPS · Terraforming Moon (solo, week 4)

**Concepts to understand**
- A first Terraform project: provider, resources.
- `init`, `plan`, `apply`, `destroy`.
- Changing infrastructure by changing code.
- Security group rules managed as code.
- Variables for values that change (e.g. allowed IPs).

**Typical pitfalls**
- Changing resources in the console, so the code and reality drift apart.

**Explain-your-own-code prompts**
- "You added an IP. What did `plan` show, and why only that?"
- "What would happen if someone changed the rule by hand in the console?"

**Related questions:** DEVOPS-IAC-01, DEVOPS-IAC-02, DEVOPS-IAC-03, DEVOPS-IAC-04
