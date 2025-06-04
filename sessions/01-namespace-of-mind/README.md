# Session 1: Namespace of Mind

This session builds intuition for how namespaces isolate workloads and control access within a Kubernetes cluster.

## Overview
A namespace is a logical partition for cluster resources. Many organizations use namespaces per environment (dev, staging, prod) or per team to keep things organized. RBAC rules often reference namespaces to restrict who can view or modify objects.

Tools like [k9s](https://k9scli.io/) or the VS Code Kubernetes extension let you filter resources by namespace, making it easier to focus on just your slice of the cluster.

## Goals
- Understand what namespaces are and why they matter
- Create and explore namespaces using `kubectl`
- Deploy applications into multiple namespaces and observe isolation
- Experiment with basic RBAC concepts

## Hands-on Steps

1. **Create a namespace**
   ```bash
   kubectl create namespace playground
   ```
   (Optional) target it by default:
   ```bash
   kubectl config set-context --current --namespace=playground
   ```

2. **Deploy the demo service**
   Use the provided `hello-deployment.yaml` manifest.
   ```bash
   kubectl apply -f hello-deployment.yaml -n playground
   kubectl get pods -n playground
   ```
   Explore the namespace with `k9s -n playground` or via the Kubernetes extension.

3. **Deploy the same service to another namespace**
   ```bash
   kubectl create namespace sandbox
   kubectl apply -f hello-deployment.yaml -n sandbox
   ```

4. **Break it and fix it**
   Introduce an invalid image tag and watch the pod fail:
   ```bash
   kubectl -n sandbox set image deployment/hello hello=nginx:badtag
   kubectl describe pod -n sandbox
   ```
   Restore a working image:
   ```bash
   kubectl -n sandbox set image deployment/hello hello=nginx:stable
   ```

5. **Clean up**
   ```bash
   kubectl delete namespace playground sandbox
   ```

_Optional_: Use [Ollama](https://ollama.ai) to prompt-generate additional namespace‑scoped manifests.
