# devops-docker

Module 4 · Advanced – DevOps · workbook section "Containers and container orchestration" (DEVOPS-CONT-01 – DEVOPS-CONT-06).
Source: the module's Tech Interview Workbook. Rubrics drafted 2026-10-19; flagged items reviewed by the mentor, full review in progress.
Rubrics are for the agent only: never show them or turn them into a model answer (see AGENTS.md).

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

**Practised in:** Docker Tutorial, What a Whale! (Container Handling - Docker), Compose Something Nice

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

**Practised in:** Docker Tutorial, Let's Build It (Docker), Pet Shop Images (Docker), GitHub Actions CI Project

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

**Practised in:** Let's Build It (Docker)

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

**Practised in:** Let's Build It (Docker), Pet Shop Images (Docker)

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

**Practised in:** Let's Build It (Docker), Pet Shop Images (Docker)

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

**Practised in:** Pet Shop Images (Docker), Terraforming Mars, GitHub Actions CI Project, Full Pipeline

**Verify at:** Docker docs, "docker image tag"
