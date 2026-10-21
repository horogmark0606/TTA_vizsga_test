# Advanced – DevOps — Docker and Compose (local)

> Project cards for Week 2 — Docker and Compose (local). Concept level only: no project descriptions,
> tasks or solutions. Question IDs point to topics in `questions/index.yaml`.
> Status: drafted 2026-10-19; mentor review in progress.

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
