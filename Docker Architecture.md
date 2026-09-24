# 🐳 Docker Architecture

Docker follows a **client-server architecture** that allows users to build, run, manage, and distribute containerized applications.

Docker architecture consists of several important components, including the **Docker Client, Docker Host, Docker Daemon, Docker Images, Docker Containers, Docker Networks, Docker Volumes, and Docker Registry**.

---

## 📌 Docker Architecture Diagram

> Save your architecture image in the repository as:
>
> `images/docker-architecture.png`

![Docker Architecture](images/docker-architecture.png)

---

# 1. Docker Client

The **Docker Client** is the primary interface used by users to interact with Docker.

The Docker Client is commonly used through the **Docker Command Line Interface (CLI)**.

When a user executes a Docker command, the Docker Client sends a request to the **Docker Daemon** through the Docker API.

### Examples

```bash
docker build
docker pull
docker run
docker ps
docker stop
docker start
docker images
docker exec
