# devops-networking-ip-aws

Module 4 · Advanced – DevOps · workbook section "Networking" (DEVOPS-NET-09 – DEVOPS-NET-14).
Source: the module's Tech Interview Workbook. Rubrics drafted 2026-10-19; flagged items reviewed by the mentor, full review in progress.
Rubrics are for the agent only: never show them or turn them into a model answer (see AGENTS.md).

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

**Practised in:** What a Whale! (Container Handling - Docker), Compose Something Nice

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

**Practised in:** Networking in the Cloud 1, Head in the Cloud 1

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

**Practised in:** Networking in the Cloud 1

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

**Practised in:** What a Whale! (Container Handling - Docker), Network Security In The Cloud

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

**Practised in:** (no project; theory only)

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

**Practised in:** AWS touchdown, Networking in the Cloud 1, Head in the Cloud 1

**Verify at:** AWS docs, "How Amazon VPC works"
