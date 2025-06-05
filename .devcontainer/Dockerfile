FROM mcr.microsoft.com/devcontainers/base:ubuntu

# Install dependencies
RUN apt-get update \
    && apt-get install -y curl ca-certificates gnupg lsb-release apt-transport-https \
    && rm -rf /var/lib/apt/lists/*

# Install kubectl
RUN curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl" \
    && chmod +x kubectl \
    && mv kubectl /usr/local/bin/

# Install helm
RUN curl -LO https://get.helm.sh/helm-v3.17.0-linux-amd64.tar.gz \
    && tar -xzf helm-v3.17.0-linux-amd64.tar.gz \
    && mv linux-amd64/helm /usr/local/bin/helm \
    && rm -rf linux-amd64 helm-v3.17.0-linux-amd64.tar.gz

# Install kind with architecture detection
RUN if [ "$(uname -m)" = "x86_64" ]; then \
        curl -Lo ./kind https://kind.sigs.k8s.io/dl/v0.29.0/kind-linux-amd64; \
    elif [ "$(uname -m)" = "aarch64" ]; then \
        curl -Lo ./kind https://kind.sigs.k8s.io/dl/v0.29.0/kind-linux-arm64; \
    fi \
    && chmod +x ./kind \
    && mv ./kind /usr/local/bin/kind

# Install Node.js LTS using NodeSource
RUN curl -fsSL https://deb.nodesource.com/setup_22.x | bash - \
    && apt-get update \
    && apt-get install -y nodejs \
    && npm install -g npm@latest \
    && rm -rf /var/lib/apt/lists/*

# Optional Ollama install script
COPY install-ollama.sh /usr/local/bin/install-ollama
RUN chmod +x /usr/local/bin/install-ollama

CMD [ "bash" ]
