# Kube and Coffee

This repository accompanies a series of talks that teach the fundamentals of Kubernetes for software engineers. Each session builds on the last and the code is separated by session for easy reference.

## Getting Started

### Prerequisites
* **Docker** – install [Docker Desktop](https://www.docker.com/products/docker-desktop/) for macOS.
* **Visual Studio Code** – with the [Dev Containers extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers).

### Using the Dev Container
1. Clone this repository.
2. Open it in VS Code and choose **Reopen in Container** when prompted.
3. The first build installs Node.js, `kubectl`, `helm` and `kind`. A local Kubernetes cluster is created automatically using `.devcontainer/kind-config.yaml` which exposes ports `11434` and `3080` on the host.
4. (Optional) Run `install-ollama` inside the dev container to add [Ollama](https://ollama.ai) for AI‑generated manifests. Example manifests for an Ollama service and a LibreChat UI are included in `sessions/01-namespace-of-mind/`.
5. CoreDNS is deployed by default so services can resolve each other via DNS.

### Repository Structure

```
.sessions/          # Each numbered folder contains examples for a talk
└── 01-namespace-of-mind/
    └── README.md   # Session notes and hands-on steps
```

You can work through the sessions in order. As the series grows, the dev container will evolve to include more tools.

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.
