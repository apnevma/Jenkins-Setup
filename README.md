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
```

2. **Start Jenkins**
```bash
docker compose up -d
```

3. **Access Jenkins**
* Open a browser and go to http://localhost:8080
* Unlock Jenkins using the password from the logs:
```bash
docker logs jenkins
```

4. **Install suggested plugins and create your first pipeline**

## Notes

* Jenkins has access to host Docker, so you can run builds that spin up containers.
* The `jenkins_home` volume ensures that job configurations persist across container restarts.
* This setup is meant for local development and learning purposes. For production use, consider security best practices for Docker socket access and volume management.