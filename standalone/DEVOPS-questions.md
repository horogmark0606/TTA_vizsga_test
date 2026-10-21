# Advanced – DevOps — interview question rubrics

> Questions come from the module's Tech Interview Workbook (students already
> have them). Rubrics are for the agent only: compare silently, never show
> them, never turn them into a model answer. See the agent instructions.
> Which projects practise each question: `DEVOPS-index.md`.
>
> Status: **draft, mentor review pending.**

---

## Linux

### DEVOPS-LINUX-01
**Question:** What kind of virtualization technologies are you familiar with?

**A good answer covers**
- hypervisor-based VMs: type 1 (bare metal, e.g. KVM, ESXi, Hyper-V) vs. type 2 (hosted, e.g. VirtualBox)
- containers (Docker, containerd): OS-level, shared kernel
- WSL 2 as a lightweight VM
- cloud instances (EC2) run on virtualisation

**Common misconceptions**
- containers are small VMs

**Interviewer follow-ups**
- "What does WSL 2 actually run under the hood?"

**Verify at:** Red Hat, "What is virtualization?"; Docker docs, "What is a container?"

### DEVOPS-LINUX-02
**Question:** What command line text manipulation tools are you familiar with?

**A good answer covers**
- `grep` (search / filter), `sed` (stream edit / replace), `awk` (fields, columns)
- `cut`, `sort`, `uniq`, `tr`, `wc`, `head`, `tail`
- `jq` for JSON
- combining them with pipes

**Common misconceptions**
- (none typical; check they can describe a use for each)

**Interviewer follow-ups**
- "Count the unique IP addresses in an access log."

**Verify at:** GNU coreutils / sed / gawk manuals; `man` pages

### DEVOPS-LINUX-03
**Question:** How would you schedule a command to run every Sunday at midnight?

**A good answer covers**
- cron: `crontab -e`
- `0 0 * * 0 command` (minute, hour, day of month, month, day of week)
- alternative: systemd timers
- full paths and environment: cron's environment is minimal

**Common misconceptions**
- day-of-week `7` vs `0` (both mean Sunday in most crons; worth checking)

**Interviewer follow-ups**
- "Your cron job works by hand but not from cron. What do you check?"

**Verify at:** `man 5 crontab`; crontab.guru

### DEVOPS-LINUX-04
**Question:** How would you check the available resources (memory, disk space, CPU)?

**A good answer covers**
- memory: `free -h`, `/proc/meminfo`
- disk: `df -h` (filesystems), `du -sh` (directories)
- CPU / load: `top` / `htop`, `uptime`, `nproc`, `lscpu`, `/proc/cpuinfo`
- `vmstat`, `iostat`

**Common misconceptions**
- `df` and `du` show the same thing

**Interviewer follow-ups**
- "`df` says the disk is full but `du` doesn't find big files. Why might that be?"

**Verify at:** `man free`, `man df`, `man top`

### DEVOPS-LINUX-05
**Question:** What are hard links and symbolic links?

**A good answer covers**
- hard link: another name for the same inode; same data
- symlink: a small file that points to a path
- delete the original: hard link still works, symlink breaks
- hard links can't cross filesystems or (usually) point to directories
- `ln` vs. `ln -s`

**Common misconceptions**
- a hard link is a copy

**Interviewer follow-ups**
- "How can you tell how many hard links a file has?"

**Verify at:** `man ln`; `man 7 symlink`

### DEVOPS-LINUX-06
**Question:** What are services in the context of Linux?

**A good answer covers**
- long-running background processes (daemons): web servers, SSH, databases
- managed by the init system (systemd units)
- `systemctl start / stop / status / enable`
- logs via `journalctl`

**Common misconceptions**
- a service is any running program

**Interviewer follow-ups**
- "How do you make a service start at boot?"

**Verify at:** `man systemctl`; systemd documentation

### DEVOPS-LINUX-07
**Question:** Describe the permission model of Linux! How would you make a file only readable and writable by its owner?

**A good answer covers**
- owner / group / others × read / write / execute
- octal (`rwx` = 4+2+1) and symbolic notation
- `chmod 600 file` (or `chmod u=rw,go= file`)
- ownership with `chown`; directories: `x` means "enter"
- root bypasses permissions; special bits (setuid, setgid, sticky)

**Common misconceptions**
- `x` on a directory means "run it"

**Interviewer follow-ups**
- "Why does SSH insist on `600` for a private key?"

**Verify at:** `man chmod`

### DEVOPS-LINUX-08
**Question:** What is the difference between Gi, Gb and GB?

**A good answer covers**
- GB: gigabyte, 10⁹ bytes (decimal)
- GiB / Gi: gibibyte, 2³⁰ bytes (binary), ~7% more
- Gb: gigabit (bits, not bytes), 1/8 of a GB
- where you meet each: disks (GB), memory / Kubernetes (Gi), network speeds (Gb/s)

**Common misconceptions**
- "they're all the same"

**Interviewer follow-ups**
- "Your new 1 TB disk shows ~931 GiB. Where did the space go?"

**Verify at:** NIST, "Prefixes for binary multiples"

### DEVOPS-LINUX-09
**Question:** What are some well-known configuration files on a Linux OS?

**A good answer covers**
- users / groups: `/etc/passwd`, `/etc/shadow`, `/etc/group`
- networking / names: `/etc/hosts`, `/etc/resolv.conf`
- mounts: `/etc/fstab`
- SSH: `/etc/ssh/sshd_config`, `~/.ssh/authorized_keys`
- shell: `~/.bashrc`, `~/.profile`; sudo: `/etc/sudoers`

**Common misconceptions**
- passwords are stored in `/etc/passwd`

**Interviewer follow-ups**
- "Why are password hashes in `/etc/shadow` and not in `/etc/passwd`?"

**Verify at:** Filesystem Hierarchy Standard; `man 5 passwd`, `man 5 shadow`

### DEVOPS-LINUX-10
**Question:** Explain the "set" builtin command and some of its most commonly used flags!

**A good answer covers**
- changes shell options (and lists variables without arguments)
- `set -e`: exit on error
- `set -u`: error on unset variables
- `set -o pipefail`: a failing command in a pipe fails the pipe
- `set -x`: print commands as they run (debugging)

**Common misconceptions**
- `set` is for setting variables (that's plain assignment)

**Interviewer follow-ups**
- "Why do many scripts start with `set -euo pipefail`?"

**Verify at:** GNU Bash manual, "The Set Builtin"

---

## Networking

### DEVOPS-NET-01
**Question:** What is a MAC address?

**A good answer covers**
- a hardware address of a network interface (48 bits, hex)
- used on the local network (layer 2)
- vs. IP addresses (layer 3, routable)
- can be changed / randomised

**Common misconceptions**
- MAC addresses are used to route across the internet

**Interviewer follow-ups**
- "How does a machine find the MAC address for an IP on its network?"

**Verify at:** Cloudflare Learning, "What is a MAC address?"

### DEVOPS-NET-02
**Question:** What is the difference between binding to 127.0.0.1 or 0.0.0.0?

**A good answer covers**
- `127.0.0.1`: loopback, only reachable from the same machine
- `0.0.0.0`: all interfaces, reachable from outside (if the firewall allows)
- why a container app must bind `0.0.0.0` to be reachable through a published port
- security implication

**Common misconceptions**
- `0.0.0.0` is an address you can connect to like any other

**Interviewer follow-ups**
- "Your app in a container works inside but not from the host. What's the likely cause?"

**Verify at:** (any networking reference); Docker docs, "Published ports"

### DEVOPS-NET-03
**Question:** What are the Layers of the OSI model?

**A good answer covers**
- 1 physical, 2 data link, 3 network, 4 transport, 5 session, 6 presentation, 7 application
- an example for some layers (Ethernet / MAC, IP, TCP / UDP, HTTP)
- TCP/IP model as the practical simplification

**Common misconceptions**
- (none typical; check order and examples)

**Interviewer follow-ups**
- "On which layer does a security group work? A load balancer?"

**Verify at:** Cloudflare Learning, "What is the OSI model?"

### DEVOPS-NET-04
**Question:** What is the difference between a router and a switch?

**A good answer covers**
- switch: connects devices in the same network, forwards by MAC (layer 2)
- router: connects different networks, forwards by IP (layer 3)
- home routers often combine both

**Common misconceptions**
- "they do the same thing"

**Interviewer follow-ups**
- "What plays the router's role in an AWS VPC?"

**Verify at:** Cisco, "What is a network switch vs. a router?"

### DEVOPS-NET-05
**Question:** What is the difference between TCP and UDP?

**A good answer covers**
- TCP: connection-oriented, reliable, ordered, retransmits; handshake
- UDP: connectionless, no delivery guarantee, lower overhead
- examples: TCP for HTTP / SSH / databases; UDP for DNS, streaming, games
- (HTTP/3 uses QUIC over UDP)

**Common misconceptions**
- UDP is "worse" (it's a different trade-off)

**Interviewer follow-ups**
- "Why does DNS mostly use UDP?"

**Verify at:** Cloudflare Learning, "TCP vs UDP"

### DEVOPS-NET-06
**Question:** What is a VPN?

**A good answer covers**
- an encrypted tunnel that makes a remote device / network appear to be on another network
- uses: remote access to private networks, site-to-site links, privacy
- examples: IPsec, WireGuard, OpenVPN; AWS Site-to-Site / Client VPN

**Common misconceptions**
- a VPN makes you anonymous

**Interviewer follow-ups**
- "How else can you reach a private subnet without a VPN?"

**Verify at:** Cloudflare Learning, "What is a VPN?"

### DEVOPS-NET-07
**Question:** What is DNS?

**A good answer covers**
- translates names to IP addresses (and more)
- hierarchy: root → TLD → authoritative servers; resolvers and caching
- record types: A, AAAA, CNAME, MX, TXT
- TTL

**Common misconceptions**
- a DNS change is visible everywhere immediately

**Interviewer follow-ups**
- "You changed a record but users still reach the old server. Why?"

**Verify at:** Cloudflare Learning, "What is DNS?"

### DEVOPS-NET-08
**Question:** What is DHCP?

**A good answer covers**
- automatically assigns IP configuration to devices (IP, mask, gateway, DNS)
- leases that expire and renew
- discover → offer → request → acknowledge

**Common misconceptions**
- DHCP resolves names (that's DNS)

**Interviewer follow-ups**
- "Why do servers often have static or reserved IPs?"

**Verify at:** Cloudflare / Microsoft docs, "DHCP overview"

### DEVOPS-NET-09
**Question:** What are some well-known ports?

**A good answer covers**
- 22 SSH, 80 HTTP, 443 HTTPS, 53 DNS
- 25 SMTP, 3306 MySQL, 5432 PostgreSQL, 6379 Redis
- well-known range 0–1023 (needs privileges to bind)

**Common misconceptions**
- (none typical; check a reasonable set)

**Interviewer follow-ups**
- "Why can't a normal user start a server on port 80 directly?"

**Verify at:** IANA, "Service Name and Transport Protocol Port Number Registry"

### DEVOPS-NET-10
**Question:** What are the private IP address ranges?

**A good answer covers**
- `10.0.0.0/8`
- `172.16.0.0/12`
- `192.168.0.0/16`
- not routed on the public internet; need NAT
- (RFC 1918)

**Common misconceptions**
- `172.0.0.0/8` is private

**Interviewer follow-ups**
- "Which range did your VPC use, and why does it matter if you connect two VPCs?"

**Verify at:** RFC 1918

### DEVOPS-NET-11
**Question:** How many usable addresses are in 192.168.1.0/24?

**A good answer covers**
- /24 → 256 addresses
- classically 254 usable (minus network and broadcast address)
- in AWS subnets: 251 (AWS reserves 5)
- how to compute it from the prefix length

**Common misconceptions**
- 256 usable

**Interviewer follow-ups**
- "How many usable addresses in a /28 in AWS?"

**Verify at:** AWS docs, "Subnet CIDR blocks" (reserved addresses)

### DEVOPS-NET-12
**Question:** What network diagnostic/debugging tools are you familiar with?

**A good answer covers**
- reachability: `ping`, `traceroute` / `mtr`
- DNS: `dig`, `nslookup`
- ports / sockets: `ss` / `netstat`, `nc`, `telnet`
- HTTP: `curl`
- packets: `tcpdump`, Wireshark
- cloud: VPC flow logs, Reachability Analyzer

**Common misconceptions**
- "ping fails, so the server is down" (ICMP may be blocked)

**Interviewer follow-ups**
- "Ping fails but `curl` works. How is that possible?"

**Verify at:** `man` pages; AWS docs, "VPC Flow Logs"

### DEVOPS-NET-13
**Question:** What is the purpose of the ARP protocol?

**A good answer covers**
- maps an IP address to a MAC address on the local network
- broadcast request, unicast reply; ARP cache
- needed before sending frames to a local host or the gateway
- ARP spoofing as a risk

**Common misconceptions**
- ARP works across routers

**Interviewer follow-ups**
- "When you reach a server on another network, whose MAC address do you look up?"

**Verify at:** Cloudflare Learning, "What is ARP?"

### DEVOPS-NET-14
**Question:** What are the basic networking components in AWS?

**A good answer covers**
- VPC (CIDR), subnets (one per AZ), public vs. private
- route tables, internet gateway, NAT gateway
- security groups and NACLs
- Elastic IPs, load balancers, VPC peering / endpoints

**Common misconceptions**
- a subnet is public because of its name (the route to an IGW decides)

**Interviewer follow-ups**
- "What exactly makes a subnet public?"

**Verify at:** AWS docs, "How Amazon VPC works"

---

## Security

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

**Verify at:** AWS, "Shared Responsibility Model"

---

## Containers and container orchestration

### DEVOPS-CONT-01
**Question:** What are the key differences between containers and virtual machines?

**A good answer covers**
- VM: full guest OS on a hypervisor; strong isolation; heavier, slower to start
- container: isolated process sharing the host kernel (namespaces, cgroups); light, fast
- containers package the app and its dependencies
- isolation trade-off

**Common misconceptions**
- containers include their own kernel

**Interviewer follow-ups**
- "Can you run a Windows container on a Linux host? Why not?"

**Verify at:** Docker docs, "What is a container?"

### DEVOPS-CONT-02
**Question:** What are the most important instructions in a Dockerfile?

**A good answer covers**
- `FROM`, `WORKDIR`, `COPY` / `ADD`, `RUN`
- `ENV`, `ARG`, `EXPOSE`, `USER`
- `CMD`, `ENTRYPOINT`
- each instruction creates a layer (most of them)

**Common misconceptions**
- `EXPOSE` publishes the port

**Interviewer follow-ups**
- "When would you use `ADD` instead of `COPY`?"

**Verify at:** Docker docs, "Dockerfile reference"

### DEVOPS-CONT-03
**Question:** What is the difference between the CMD and the ENTRYPOINT instructions?

**A good answer covers**
- `ENTRYPOINT`: the executable that always runs
- `CMD`: default command or default arguments; easily overridden at `docker run`
- together: `ENTRYPOINT` = program, `CMD` = default args
- exec form vs. shell form (signals, PID 1)

**Common misconceptions**
- they're interchangeable

**Interviewer follow-ups**
- "Why does the exec form matter for stopping a container cleanly?"

**Verify at:** Docker docs, "Dockerfile reference" (CMD, ENTRYPOINT)

### DEVOPS-CONT-04
**Question:** How does caching work in docker builds?

**A good answer covers**
- each instruction's result is cached as a layer
- a changed instruction or changed copied files invalidate that layer **and all after it**
- order: rarely changing steps first (dependencies), often changing last (source)
- `--no-cache`; cache in CI (cache-from / BuildKit)

**Common misconceptions**
- only the changed layer is rebuilt

**Interviewer follow-ups**
- "Why copy the dependency manifest before the rest of the source?"

**Verify at:** Docker docs, "Docker build cache"

### DEVOPS-CONT-05
**Question:** What are some common practices for optimizing container image size?

**A good answer covers**
- small base images (alpine, slim, distroless)
- multi-stage builds: build tools stay out of the final image
- combine and clean up in the same `RUN` (package caches)
- `.dockerignore`
- install only production dependencies

**Common misconceptions**
- deleting files in a later layer makes the image smaller

**Interviewer follow-ups**
- "Why doesn't `RUN rm` in a later step shrink the image?"

**Verify at:** Docker docs, "Building best practices"

### DEVOPS-CONT-06
**Question:** What problems can occur when the "latest" tag is used?

**A good answer covers**
- `latest` is just a default tag name, not "newest"
- not reproducible: different machines / times pull different images
- hard to roll back or know what's deployed
- caching: hosts may not pull the new image
- use explicit versions or commit SHAs (or digests)

**Common misconceptions**
- `latest` always points to the most recent build

**Interviewer follow-ups**
- "How did your pipeline tag images, and why?"

**Verify at:** Docker docs, "docker image tag"

### DEVOPS-CONT-07
**Question:** Explain the architecture of a Kubernetes cluster!

**A good answer covers**
- control plane: API server, etcd, scheduler, controller manager
- worker nodes: kubelet, container runtime, kube-proxy
- Pods run on nodes; everything goes through the API server
- desired state and reconciliation

**Common misconceptions**
- kubectl talks to the nodes directly

**Interviewer follow-ups**
- "What happens, component by component, when you apply a Deployment?"

**Verify at:** Kubernetes docs, "Cluster Architecture"

### DEVOPS-CONT-08
**Question:** What is the Deployment Kubernetes object responsible for?

**A good answer covers**
- declares the desired state of a set of identical Pods (image, replicas)
- manages ReplicaSets; replaces failed Pods
- rolling updates and rollbacks
- scaling by changing replicas

**Common misconceptions**
- a Deployment *is* the Pod

**Interviewer follow-ups**
- "You delete a Pod of a Deployment. What happens and why?"

**Verify at:** Kubernetes docs, "Deployments"

### DEVOPS-CONT-09
**Question:** What kind of probes are there in Kubernetes, and what are their use cases?

**A good answer covers**
- liveness: is it alive? failing → container restarted
- readiness: ready to receive traffic? failing → removed from Service endpoints
- startup: for slow starters; holds off the other probes
- types: HTTP, TCP, exec (and gRPC)

**Common misconceptions**
- readiness failure restarts the container

**Interviewer follow-ups**
- "Why can a badly set liveness probe cause a restart loop?"

**Verify at:** Kubernetes docs, "Liveness, Readiness, and Startup Probes"

### DEVOPS-CONT-10
**Question:** What is the difference between resource Limit and Request?

**A good answer covers**
- request: what the scheduler reserves; used to place the Pod
- limit: the maximum the container may use
- CPU over limit → throttled; memory over limit → killed (OOMKilled)
- units: millicores (`500m`), memory in Mi / Gi

**Common misconceptions**
- requests limit usage

**Interviewer follow-ups**
- "A Pod keeps getting OOMKilled. What do you look at?"

**Verify at:** Kubernetes docs, "Resource Management for Pods and Containers"

### DEVOPS-CONT-11
**Question:** What is the Service Kubernetes object responsible for?

**A good answer covers**
- a stable name and IP for a changing set of Pods
- selects Pods by labels; load-balances between them
- types: ClusterIP, NodePort, LoadBalancer (and ExternalName)
- cluster DNS name

**Common misconceptions**
- a Service runs the containers

**Interviewer follow-ups**
- "Your Service has no endpoints. What do you check first?"

**Verify at:** Kubernetes docs, "Service"

### DEVOPS-CONT-12
**Question:** What are the main differences between ConfigMaps and Secrets?

**A good answer covers**
- both inject configuration as environment variables or files
- ConfigMap: non-sensitive config
- Secret: sensitive data; base64-encoded (not encrypted by default), access can be restricted, encryption at rest can be enabled
- keep secrets out of images and git

**Common misconceptions**
- Secrets are encrypted by default

**Interviewer follow-ups**
- "What's the Docker Compose equivalent of each in your stack?"

**Verify at:** Kubernetes docs, "ConfigMaps", "Secrets"

---

## Infrastructure as Code

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

**Verify at:** Terraform docs, "Style Guide"
