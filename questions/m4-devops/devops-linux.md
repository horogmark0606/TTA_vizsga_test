# devops-linux

Module 4 · Advanced – DevOps · workbook section "Linux" (DEVOPS-LINUX-01 – DEVOPS-LINUX-10).
Source: the module's Tech Interview Workbook. Rubrics drafted 2026-10-19; flagged items reviewed by the mentor, full review in progress.
Rubrics are for the agent only: never show them or turn them into a model answer (see AGENTS.md).

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

**Practised in:** Docker Tutorial, AWS touchdown

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

**Practised in:** Bash Scripting, Text and File Manipulation

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

**Practised in:** (no project; theory only)

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

**Practised in:** Everything is a File, Boot Process and Process Management, Widgets.sh

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

**Practised in:** Everything is a File

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

**Practised in:** Boot Process and Process Management

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

**Practised in:** Linux Permissions, The Way to a Dev's Heart is via SSH

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

**Practised in:** Everything is a File

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

**Practised in:** Path to Absolute Relativity, Linux Permissions, Widgets.sh

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

**Practised in:** Hello World, Bash Scripting, Widgets.sh

**Verify at:** GNU Bash manual, "The Set Builtin"
