# Jenkins Docker Setup

This repository contains a **Docker Compose configuration to run Jenkins in a container** with access to the host Docker engine. It is designed for local development, CI/CD experimentation, or as a starting point for more complex Jenkins pipelines.

---

## Description

- **Jenkins Container**: Runs the official Jenkins LTS image.
- **Persistent Storage**: Jenkins home directory is persisted in a Docker volume (`jenkins_home`) to retain jobs and configurations.
- **Docker Access**: The container has access to the host Docker daemon (`/var/run/docker.sock`) so Jenkins can build and manage Docker containers.
- **Ports**:
  - `8080` – Jenkins web interface
  - `50000` – Jenkins agent connections

This setup allows you to experiment with Jenkins pipelines, Docker builds, and CI/CD workflows in an isolated containerized environment.

---

## Getting Started

1. **Clone the repository**

```bash
git clone <https://github.com/apnevma/Jenkins-Setup.git>
cd <Jenkins-Setup>