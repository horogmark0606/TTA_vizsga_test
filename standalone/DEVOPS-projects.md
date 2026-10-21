# Advanced – DevOps — project cards

> Module 4 (DevOps track) of the FullStack course: Linux and Bash, Docker
> and Compose, AWS networking and security, Terraform, CI/CD with GitHub
> Actions, Kubernetes. Question IDs (`DEVOPS-…`) refer to
> `DEVOPS-questions.md`.
>
> Status: **draft, mentor review pending.**

---

## Week 1 — Linux / WSL

### DEVOPS · Path to Absolute Relativity (solo, week 1)

**Concepts to understand**
- Absolute vs. relative paths.
- The current working directory, and how a relative path is resolved from it.
- `.` and `..`.
- CSV as a simple data format.

**Typical pitfalls**
- A script that only works when started from one particular directory.

**Explain-your-own-code prompts**
- "Given this relative path and this working directory, how do you get the absolute path, step by step?"

**Related questions:** DEVOPS-LINUX-09

### DEVOPS · Everything is a File (solo, week 1)

**Concepts to understand**
- The Unix idea that devices, sockets and processes appear as files.
- Block devices, filesystems, mount points; a disk image mounted through a loop device.
- The kinds of filesystem entries (plain files, folders, two kinds of links) and how to tell them apart.
- Hidden files.
- Archiving vs. compressing.
- Checking disk usage, and what happens when a filesystem is full.

**Typical pitfalls**
- Thinking a hard link and a symlink behave the same when the original is deleted.

**Explain-your-own-code prompts**
- "Delete the original file. What happens to the hard link, and to the symlink? Why?"
- "What did you actually create, format and mount? In what order?"

**Related questions:** DEVOPS-LINUX-04, DEVOPS-LINUX-05, DEVOPS-LINUX-08

### DEVOPS · Linux Permissions (solo, week 1)

**Concepts to understand**
- Read / write / execute for owner, group, others; octal and symbolic `chmod`.
- Ownership and `chown`.
- Special permissions (setuid, setgid, sticky bit).
- Users and groups; the files that store them, including password hashes.
- Inodes and file metadata.
- What the server checks when someone logs in with a key, and why those files need strict permissions.
- Giving a user admin rights through a group.

**Typical pitfalls**
- Making things work with `777`.
- Wrong ownership on SSH files, so key login silently fails.

**Explain-your-own-code prompts**
- "Read me the permissions of the SSH files you set up, and explain why they must be exactly like that."
- "What's the difference between `chmod 640` and `chmod u=rw,g=r`?"

**Related questions:** DEVOPS-LINUX-07, DEVOPS-LINUX-09, DEVOPS-SEC-07

### DEVOPS · Boot Process and Process Management (solo, week 1)

**Concepts to understand**
- Stages of booting a Linux server; the bootloader, and why WSL skips it.
- The init system (systemd) as PID 1; services and their start-up time.
- Listing processes; PID and PPID.
- Foreground, background, stopped jobs; job control.
- Subshells.

**Typical pitfalls**
- Confusing stopping a process with terminating it.

**Explain-your-own-code prompts**
- "You started a long-running command. How did you pause it, and then continue it in the background?"
- "Which process is the parent of your subshell? How did you find out?"

**Related questions:** DEVOPS-LINUX-04, DEVOPS-LINUX-06

### DEVOPS · The Way to a Dev's Heart is via SSH (solo, week 1)

**Concepts to understand**
- What SSH is and how a key-based login works.
- Symmetric vs. asymmetric encryption.
- Creating a key pair with a comment; key size and type.
- Correct permissions for the SSH directory and the keys.
- Encrypting a message with someone's public key and decrypting it with your private key.

**Typical pitfalls**
- Sharing the private key instead of the public one.
- Keys rejected because their permissions are too open.

**Explain-your-own-code prompts**
- "Which key did you give your classmate, and why is that safe?"
- "Why does SSH reject a key file with loose permissions?"

**Related questions:** DEVOPS-SEC-06, DEVOPS-LINUX-07

### DEVOPS · Hello World (solo, week 1)

**Concepts to understand**
- Printing in Bash.
- Defining and calling functions.
- "Returning" values from Bash functions: output vs. exit status.
- Reading user input, with a fallback when it's empty.
- Script arguments.
- Separating concerns into small functions.

**Typical pitfalls**
- Using `return` to give back a string (it only sets the exit status).

**Explain-your-own-code prompts**
- "How does your function give its message back to the caller? Why not with `return`?"

**Related questions:** DEVOPS-LINUX-10

### DEVOPS · Bash Scripting (team, week 1)

**Concepts to understand**
- stdin, stdout, stderr; redirection; `>` vs. `>>`.
- Variables: global vs. local; environment variables.
- Functions with arguments.
- Arrays in Bash.
- Strict-mode flags for safer scripts.

**Typical pitfalls**
- Unquoted variables breaking on spaces.
- Overwriting a file with `>` when you meant to append.

**Explain-your-own-code prompts**
- "Where does your error output go? How would you send it to a file?"
- "Which variables are local, and why?"

**Related questions:** DEVOPS-LINUX-02, DEVOPS-LINUX-10

### DEVOPS · Text and File Manipulation (team, week 1)

**Concepts to understand**
- Filtering and transforming text with `grep`, `sed`, `awk`.
- `head` / `tail` and line ranges.
- Querying JSON with `jq`.
- Compressing vs. archiving; `gzip`, `bzip2`, `tar`.
- Building pipelines from small tools.

**Typical pitfalls**
- A regex that matches more than intended.

**Explain-your-own-code prompts**
- "Explain one of your pipelines piece by piece. What goes in and out of each command?"
- "What's the difference between a `.tar` and a `.tar.gz`?"

**Related questions:** DEVOPS-LINUX-02

### DEVOPS · Widgets.sh (team, week 1)

**Concepts to understand**
- Reading system information from the files Linux exposes (memory, CPU, processes).
- Disks, free space, block devices.
- Users and groups, and telling system accounts from real ones.
- Environment variables controlling a script's behaviour.
- Control structures in Bash.

**Typical pitfalls**
- Parsing human-formatted command output that changes between systems.

**Explain-your-own-code prompts**
- "Where does your script get the memory numbers from? Is it a real file?"
- "How does an environment variable change what your script prints?"

**Related questions:** DEVOPS-LINUX-04, DEVOPS-LINUX-09, DEVOPS-LINUX-10

---

## Week 2 — Docker and Compose (local)

### DEVOPS · Docker Tutorial (solo, week 2)

**Concepts to understand**
- Images vs. containers.
- A Dockerfile and building an image.
- Registries (Docker Hub).
- Named volumes vs. bind mounts.
- Container networks.
- Docker Compose basics.

**Typical pitfalls**
- Data lost because it was written inside the container, not in a volume.

**Explain-your-own-code prompts**
- "What's the difference between the image and the container you started from it?"
- "Where does your data live when the container is removed?"

**Related questions:** DEVOPS-CONT-01, DEVOPS-CONT-02, DEVOPS-LINUX-01

### DEVOPS · What a Whale! (Container Handling - Docker) (solo, week 2)

**Concepts to understand**
- Reading an image's registry page (tags, environment variables, ports, volumes).
- Running containers: detached mode, port publishing, start / stop / remove, exec.
- Bind mounts.
- Networks: bridge vs. host; connecting containers.
- Debugging: logs, inspect.
- Clean-up (prune).

**Typical pitfalls**
- Confusing host port and container port.
- Containers on different networks can't reach each other by name.

**Explain-your-own-code prompts**
- "In your port mapping, which number is the host and which is the container?"
- "How did two containers find each other?"

**Related questions:** DEVOPS-CONT-01, DEVOPS-NET-02, DEVOPS-NET-09, DEVOPS-NET-12

### DEVOPS · Let's Build It (Docker) (solo, week 2)

**Concepts to understand**
- Image layers.
- The main Dockerfile instructions.
- Build context.
- The build cache and how instruction order affects it.
- Tagging and publishing images.
- Multi-stage builds to shrink images.

**Typical pitfalls**
- Copying everything before installing dependencies, which breaks caching.
- A huge image because build tools stay in the final stage.

**Explain-your-own-code prompts**
- "Change one source file and rebuild. Which layers are rebuilt, and why?"
- "How did you make the image smaller?"

**Related questions:** DEVOPS-CONT-02, DEVOPS-CONT-03, DEVOPS-CONT-04, DEVOPS-CONT-05

### DEVOPS · Pet Shop Images (Docker) (solo, week 2)

**Concepts to understand**
- Writing Dockerfiles for an existing application from its documentation.
- Different needs for a backend and a frontend image.
- Multi-stage builds.
- Analysing images (history, size).
- Investigating the build cache.

**Typical pitfalls**
- Running as root inside the image without a reason.

**Explain-your-own-code prompts**
- "Why does your frontend image look so different from your backend image?"
- "What did the image history tell you?"

**Related questions:** DEVOPS-CONT-02, DEVOPS-CONT-04, DEVOPS-CONT-05, DEVOPS-CONT-06

### DEVOPS · Compose Something Nice (solo, week 2)

**Concepts to understand**
- Reading and changing a Compose file.
- Defining services, their dependencies and environment variables.
- The Compose commands for starting, stopping, running one-off commands and reading logs.
- Named volumes for persistent database data.
- Separate networks to isolate services.
- Exposing a port only when needed.

**Typical pitfalls**
- Database data lost on restart (no volume).
- Exposing the database to the host when only the backend needs it.

**Explain-your-own-code prompts**
- "Which service can talk to which, and how did you enforce that?"
- "Why does the database survive a restart now?"

**Related questions:** DEVOPS-CONT-01, DEVOPS-CONT-12, DEVOPS-NET-09

---

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

---

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

---

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

---

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
