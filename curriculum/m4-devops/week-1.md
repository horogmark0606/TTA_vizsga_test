# Advanced – DevOps — Linux / WSL

> Project cards for Week 1 — Linux / WSL. Concept level only: no project descriptions,
> tasks or solutions. Question IDs point to topics in `questions/index.yaml`.
> Status: drafted 2026-10-19; mentor review in progress.

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
