# Practice tasks: DevOps practical (FullStack 2026 trial)

Practice variants for section 4 of `fullstack-2026-trial.md`. These are **not the real interview tasks**.
T1 is an example the mentor gave; the others were drafted for practice in the same style. None is a course project.
"Check for" is for the agent only (same rules as a rubric: compare silently, never reveal it, no solution).

Budget: 30 minutes each, including showing that it works. The student runs everything themselves (`docker build`,
`docker run`, the script, a push to their own test repo, `terraform fmt` / `init` / `validate` / `plan`).
`terraform init` downloads the AWS provider (a few hundred MB). `terraform apply` only in the student's own AWS
account, with free resources, and `terraform destroy` right after. The agent never handles credentials or state files.

## Dockerfile

### D1 · Containerise a small Node.js API
The app: `server.js` and `package.json`; it listens on the port in the `PORT` environment variable.
Write a `Dockerfile` and a `.dockerignore`, then the commands to build the image and run it on host port 8080.
- Check for: small base image with a fixed tag; dependency files copied before the source (cache); `npm ci`
  or equivalent; `PORT` set or passed; port mapping in `docker run`; `node_modules` in `.dockerignore`; non-root user (bonus)
- Follow-ups: "Why this order of `COPY` lines?" · "What changes if you add a dependency?" · "`EXPOSE` vs `-p`?"
- Verify at: https://docs.docker.com/build/building/best-practices/

### D2 · Multi-stage build for a Java app
A Maven project that builds into one runnable jar. Write a `Dockerfile` with a build stage and a slim runtime stage.
- Check for: build stage with JDK and Maven; runtime stage with a JRE only; only the jar copied across;
  dependency download cached before the source copy (bonus); `ENTRYPOINT` or `CMD` running the jar
- Follow-ups: "What is in the final image, and what isn't?" · "Why not a single stage?" · "`ENTRYPOINT` vs `CMD`?"
- Verify at: https://docs.docker.com/build/building/multi-stage/

### D3 · A command-line script in a container
A Python script `report.py` (with a `requirements.txt`) reads a CSV file given as an argument and prints a
summary. Write a `Dockerfile` so that `docker run <image> data/sales.csv` works on a file from a folder on
the host. Show the `docker run` command.
- Check for: Python base image with a fixed tag; `requirements.txt` installed before the source copy (cache);
  `ENTRYPOINT` for the script so arguments pass through; a bind mount for the host folder; `WORKDIR`
- Follow-ups: "Why `ENTRYPOINT` here and not only `CMD`?" · "Where does the file live: in the image or on the host?" · "What happens to output written inside the container?"
- Verify at: https://docs.docker.com/reference/dockerfile/ and https://docs.docker.com/engine/storage/bind-mounts/

## Image build process

### B1 · Release images from git tags
A repository with a working `Dockerfile`. Write a GitHub Actions workflow: when a tag like `v1.4.0` is pushed,
build the image and push it to GitHub Container Registry (GHCR) tagged with that version. Pull requests
should only build the image, never push it.
- Check for: triggers for tags matching `v*` and for pull requests; the version taken from the tag; login
  with the workflow's built-in token and the `packages: write` permission (no personal password in the file);
  push only on tags
- Follow-ups: "Why can this workflow push without a password you created?" · "What should happen if the build fails on a pull request?" · "Why version tags rather than only `latest`?"
- Verify at: https://docs.github.com/en/actions and https://github.com/docker/build-push-action

### B2 · A build script with a smoke test
Write `build.sh`: build the image, tag it with a version given as an argument and with `latest`, start a
container, check that `curl http://localhost:8080/health` returns 200, then stop and remove the container.
The script must exit with an error code if any step fails.
- Check for: argument check; `set -e` or explicit error handling; both tags; a wait or retry before `curl`;
  cleanup even when the check fails (bonus: `trap`)
- Follow-ups: "What happens if the container isn't ready yet?" · "How does CI know the script failed?"
- Verify at: https://docs.docker.com/reference/cli/docker/ and `man bash`

## Terraform (AWS)

### T1 · S3 bucket and an IAM user with access to it (from the mentor)
Create an S3 bucket. Also create an IAM User that has full access to that bucket.
- Check for: AWS provider and region; bucket resource; IAM user; a policy attached to the user; the policy
  scoped to this bucket only (both the bucket ARN and the objects inside it), not `*`; references between
  resources instead of copied names
- Follow-ups: "Why two ARNs in the policy?" · "What does 'full access' include, and is it a good idea?" · "How would the user get access keys, and where should they not end up?"
- Verify at: https://registry.terraform.io/providers/hashicorp/aws/latest/docs and
  https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_elements.html

### T2 · Read-only group for a bucket
Create an IAM group `developers` with read-only access to one existing bucket (its name is a variable), and
create the users listed in a variable (a list of names) as members of the group.
- Check for: variables with types; group, group policy (read and list only) and membership; one user per
  name with `for_each` or `count`; no hard-coded names
- Follow-ups: "`for_each` vs `count`: what happens when you remove a name from the middle?" · "Why attach the policy to the group, not the users?"
- Verify at: https://developer.hashicorp.com/terraform/language

### T3 · Buckets with retention rules
Create several S3 buckets from one map variable (bucket name → number of days to keep objects). Each bucket
gets a lifecycle rule that deletes objects after its number of days. Output a map of bucket name → ARN.
- Check for: a typed map variable; one resource block with `for_each` over the map; a lifecycle
  configuration per bucket using the map value; an output built with a `for` expression; no copy-pasted blocks
- Follow-ups: "What happens to the existing buckets when you add a new entry to the map?" · "What if two people pick the same bucket name?" · "How would you add the same tags to everything?"
- Verify at: https://registry.terraform.io/providers/hashicorp/aws/latest/docs and https://developer.hashicorp.com/terraform/language
