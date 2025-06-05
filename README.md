# Kube and Coffee

Welcome to **Kube and Coffee**—our collaborative Kubernetes learning lab! This repository accompanies a series of hands-on sessions where we explore the fundamentals of Kubernetes together, building our skills one session at a time. Each session is self-contained, so we can experiment, break things, and learn as a team.

## 📚 Session Index

| Session | Topic                                 | Summary                                              | Link                                                      |
|---------|---------------------------------------|------------------------------------------------------|-----------------------------------------------------------|
| 01      | Namespace of Mind                    | Namespaces, isolation, and RBAC basics               | [Session 1 README](sessions/01-namespace-of-mind/README.md) |
| 02      | What's in a Pod?                     | Pod lifecycle, deployments, init containers, sidecars| [Session 2 README](sessions/02-whats-in-a-pod/README.md)    |
| 03      | Keeping Secrets, Sharing Configs      | ConfigMaps, Secrets, and configuration management     | [Session 3 README](sessions/03-keeping-secrets-sharing-configs/README.md) |
| 04      | PVC You Later                        | Persistent storage and StatefulSets                   | [Session 4 README](sessions/04-pvc-you-later/README.md)     |
| 05      | Pods that Scale Themselves            | Autoscaling and metrics-driven behavior               | [Session 5 README](sessions/05-pods-that-scale-themselves/README.md) |
| 06      | Bring the Helm Down                  | Helm templating and packaging                        | [Session 6 README](sessions/06-bring-the-helm-down/README.md) |
| 07      | Mesh and Tell                        | Service meshes and sidecar networking                | [Session 7 README](sessions/07-mesh-and-tell/README.md)     |
| ...     | ...                                   | ...                                                  | ...                                                       |

## Getting Started

### Prerequisites
* **Docker** – install [Docker Desktop](https://www.docker.com/products/docker-desktop/) for macOS.
* **Visual Studio Code** – with the [Dev Containers extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers).

### Using Our Dev Container
1. Clone this repository.
2. Open it in VS Code and choose **Reopen in Container** when prompted.
3. The first build sets up Node.js, `kubectl`, `helm`, and `kind`. Our local Kubernetes cluster is created automatically using `.devcontainer/kind-config.yaml`, exposing ports `11434` and `3080` on the host for easy access.
4. (Optional) Run `install-ollama` inside the dev container to add [Ollama](https://ollama.ai) for AI‑generated manifests. Example manifests for an Ollama service and a chat UI are included in `sessions/01-namespace-of-mind/`.
5. CoreDNS is deployed by default so our services can resolve each other via DNS.

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.
