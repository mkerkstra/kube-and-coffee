# Kube and Coffee

Welcome to **Kube and Coffee**—our collaborative Kubernetes learning lab! This repository accompanies a series of hands-on sessions where we explore the fundamentals of Kubernetes together, building our skills one session at a time. Each session is self-contained, so we can experiment, break things, and learn as a team.

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

### Repository Structure

```
sessions/            # Each numbered folder contains examples for a session
└── 01-namespace-of-mind/
    └── README.md   # Session notes, diagrams, and hands-on steps
```

We can work through the sessions in order, or jump in wherever we're most curious. As our series grows, the dev container will evolve to include more tools and examples for us to explore together.

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.
