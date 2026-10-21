# devops-networking-basics

Module 4 · Advanced – DevOps · workbook section "Networking" (DEVOPS-NET-01 – DEVOPS-NET-08).
Source: the module's Tech Interview Workbook. Rubrics drafted 2026-10-19; flagged items reviewed by the mentor, full review in progress.
Rubrics are for the agent only: never show them or turn them into a model answer (see AGENTS.md).

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

**Practised in:** (no project; theory only)

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

**Practised in:** What a Whale! (Container Handling - Docker)

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

**Practised in:** (no project; theory only)

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

**Practised in:** (no project; theory only)

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

**Practised in:** (no project; theory only)

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

**Practised in:** (no project; theory only)

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

**Practised in:** (no project; theory only)

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

**Practised in:** (no project; theory only)

**Verify at:** Cloudflare / Microsoft docs, "DHCP overview"
