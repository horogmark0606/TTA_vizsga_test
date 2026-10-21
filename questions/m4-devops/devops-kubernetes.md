# devops-kubernetes

Module 4 · Advanced – DevOps · workbook section "Containers and container orchestration" (DEVOPS-CONT-07 – DEVOPS-CONT-12).
Source: the module's Tech Interview Workbook. Rubrics drafted 2026-10-19; flagged items reviewed by the mentor, full review in progress.
Rubrics are for the agent only: never show them or turn them into a model answer (see AGENTS.md).

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

**Practised in:** Minikube Tutorial

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

**Practised in:** Minikube Tutorial, Make k8s Declarative

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

**Practised in:** (no project; theory only)

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

**Practised in:** (no project; theory only)

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

**Practised in:** Minikube Tutorial, Make k8s Declarative

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

**Practised in:** Compose Something Nice

**Verify at:** Kubernetes docs, "ConfigMaps", "Secrets"
