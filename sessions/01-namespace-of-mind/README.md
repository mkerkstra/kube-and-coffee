# Session 1: Namespace of Mind

This session builds intuition for how namespaces isolate workloads and control access.

## Goals
* Understand what namespaces are and why they matter
* Create and explore namespaces using `kubectl`
* Deploy applications into multiple namespaces and observe isolation
* Experiment with RBAC basics

## Exercises
1. Create a namespace and deploy a service in it.
2. Explore namespace‑scoped commands (`kubectl get pods -n <name>`).
3. Deploy a second instance of the same service in another namespace.
4. Break something and fix it.

_Optional_: Use [Ollama](https://ollama.ai) to generate namespace‑scoped manifests.
