# Docker
# Docker – Complete Theory Notes

## 1. What is Docker?

Docker is an open-source containerization platform used to package, distribute, and run applications in isolated environments called containers.

A Docker container contains the application code along with the required libraries, dependencies, configuration, and runtime environment.

Docker helps ensure that an application behaves consistently across different environments such as development, testing, and production.

---

## 2. What is Containerization?

Containerization is the process of packaging an application and its dependencies into a lightweight, isolated container.

Unlike traditional deployment, where applications depend heavily on the host operating system, containers provide a consistent environment for running applications.

Containers share the host operating system kernel, which makes them lighter and faster than traditional virtual machines.

---

## 3. Docker Image

A Docker image is a read-only template used to create containers.

An image contains everything required to run an application, including:

- Application code
- Runtime
- Libraries
- Dependencies
- Configuration
- Required system files

Images are built using a Dockerfile and can be stored in container registries such as Docker Hub.

---

## 4. Docker Container

A container is a running instance of a Docker image.

Containers provide an isolated environment for applications while sharing the host machine's operating system kernel.

A container is generally lightweight, portable, and can be started or stopped quickly.

Multiple containers can run on the same host without directly interfering with each other.

---

## 5. Dockerfile

A Dockerfile is a text file containing instructions used to build a Docker image.

It defines the base image, application files, dependencies, environment configuration, exposed ports, and commands required to run the application.

Common Dockerfile instructions include:

- `FROM` – Defines the base image.
- `WORKDIR` – Sets the working directory.
- `COPY` – Copies files from the host into the image.
- `ADD` – Adds files or resources to the image.
- `RUN` – Executes commands during image creation.
- `ENV` – Defines environment variables.
- `EXPOSE` – Documents the application's listening port.
- `CMD` – Defines the default command for the container.
- `ENTRYPOINT` – Defines the main executable of the container.

---

## 6. Docker Engine

Docker Engine is the core technology responsible for building and running Docker containers.

It consists of components that communicate with each other to manage images, containers, networks, and volumes.

Docker Engine allows developers and administrators to create, run, stop, and manage containers on a host machine.

---

## 7. Docker Architecture

Docker follows a client-server architecture.

The major components are:

### Docker Client

The Docker Client is the command-line interface used to interact with Docker.

It sends requests to the Docker daemon.

### Docker Daemon

The Docker daemon is responsible for managing Docker objects such as:

- Images
- Containers
- Networks
- Volumes

### Docker Registry

A registry stores and distributes Docker images.

Docker Hub is a commonly used public Docker registry.

---

## 8. Docker Hub

Docker Hub is a cloud-based container registry used to store, share, and distribute Docker images.

Developers can upload images to Docker Hub and make them available for use on other machines.

Docker Hub can contain both public and private repositories.

---

## 9. Docker Registry

A Docker registry is a storage and distribution system for Docker images.

Registries allow users and organizations to store image versions and retrieve them when required.

Examples include:

- Docker Hub
- Amazon Elastic Container Registry (ECR)
- GitHub Container Registry
- Google Artifact Registry
- Azure Container Registry

---

## 10. Docker Compose

Docker Compose is a tool used to define and manage multi-container applications.

A Compose configuration is generally written in a YAML file.

It allows multiple services such as:

- Frontend
- Backend
- Database
- Cache

to be defined and managed as part of one application environment.

Docker Compose is particularly useful when an application requires multiple containers that need to communicate with each other.

---

## 11. Docker Networking

Docker networking allows containers to communicate with each other and with external networks.

Containers can communicate using Docker networks without exposing every internal service directly to the host.

Docker provides different networking options depending on the application requirements.

Common network types include:

- Bridge
- Host
- None
- Overlay

The bridge network is commonly used for communication between containers on a single Docker host.

---

## 12. Docker Volume

Containers are generally designed to be replaceable and their writable data can be lost when a container is removed.

Docker volumes provide persistent storage for containerized applications.

Volumes are commonly used for databases and applications that need data to survive container recreation.

For example, a database container can store its database files in a Docker volume instead of storing them only inside the container.

---

## 13. Docker Multi-Stage Build

A multi-stage Docker build uses multiple `FROM` instructions in a single Dockerfile.

Different stages can be used for different purposes.

For example, one stage can contain build tools and dependencies, while the final stage contains only the files required to run the application.

This helps create smaller and cleaner production images.

### Benefits

- Reduces final image size
- Removes unnecessary build dependencies
- Improves image organization
- Creates cleaner production containers
- Reduces the number of unnecessary packages in the final image

---

## 14. Docker Image Layers

Docker images are built using multiple layers.

Many Dockerfile instructions create filesystem layers that become part of the image.

Docker uses these layers to improve build efficiency and reuse unchanged parts of an image.

When a Dockerfile changes, Docker can reuse previously built layers when possible.

This caching mechanism can significantly improve build performance.

---

## 15. Docker Container vs Virtual Machine

Docker containers and virtual machines provide isolation, but they use different approaches.

### Containers

Containers share the host operating system kernel and contain the application and its dependencies.

They are generally lightweight and start quickly.

### Virtual Machines

Virtual machines contain a complete guest operating system and run through a hypervisor.

They generally require more memory and storage because each virtual machine includes its own operating system.

The choice between containers and virtual machines depends on the application's requirements.

---

## 16. Docker Image vs Container

A Docker image is a static template.

A Docker container is a running instance created from that image.

An image can be used to create multiple containers.

For example, one application image can be used to create several identical containers.

---

## 17. Docker Port Mapping

Containers have their own network environment.

Port mapping allows a port on the host machine to be connected to a port inside a container.

For example, a web application running on port `80` inside a container can be made accessible through another port on the host.

This allows external users to access services running inside containers.

---

## 18. Docker Environment Variables

Environment variables allow configuration values to be passed to containers without hardcoding them directly into application code.

They are commonly used for values such as:

- Database host
- Database port
- Application environment
- Configuration settings

Sensitive information such as passwords and API keys should be handled securely rather than being permanently written into Dockerfiles or images.

---

## 19. Docker Image Tagging

Tags are used to identify different versions or variants of Docker images.

For example:

`myapp:latest`

Here:

- `myapp` is the image repository name.
- `latest` is the image tag.

Tags help identify and manage different application versions.

---

## 20. Docker Image Optimization

Docker images should contain only the components required to run the application.

Common optimization techniques include:

- Using lightweight base images
- Using multi-stage builds
- Removing unnecessary packages
- Avoiding unnecessary files
- Using `.dockerignore`
- Combining appropriate build operations
- Keeping production dependencies separate from build dependencies

Smaller images generally require less storage and can be transferred and deployed more efficiently.

---

## 21. Docker Security

Docker security is important when running applications in containers.

Important security practices include:

- Use trusted base images.
- Keep images updated.
- Avoid running applications as root when possible.
- Do not store passwords or secrets directly in Dockerfiles.
- Scan images for vulnerabilities.
- Use only required packages.
- Limit container privileges.
- Keep unnecessary ports closed.
- Use appropriate network isolation.

Containerization provides isolation, but it should not be treated as a complete security boundary by itself.

---

## 22. Advantages of Docker

Docker provides several benefits:

- Application portability
- Consistent environments
- Lightweight application isolation
- Faster application startup
- Efficient resource utilization
- Simplified deployment
- Easier application scaling
- Dependency isolation
- Reproducible environments

---

## 23. Limitations of Docker

Docker also has some limitations:

- Containers share the host kernel.
- Persistent storage requires proper planning.
- Container security requires careful configuration.
- Networking can become complex in large environments.
- Managing many containers manually can become difficult.
- Stateful applications require additional considerations.

For large-scale container environments, orchestration platforms such as Kubernetes can be used.

---

## 24. Docker in DevOps

Docker is widely used in DevOps to standardize application environments and simplify deployment.

Developers can package applications into images that contain the required dependencies.

The same image can then be used across development, testing, staging, and production environments.

This reduces differences between environments and supports consistent application delivery.

---

## 25. Key Docker Concepts

The most important Docker concepts are:

**Image** → Template containing the application and dependencies.

**Container** → Running instance of an image.

**Dockerfile** → Instructions used to build an image.

**Docker Engine** → Technology responsible for running and managing containers.

**Docker Compose** → Tool for managing multi-container applications.

**Registry** → Storage and distribution system for Docker images.

**Volume** → Persistent storage for container data.

**Network** → Communication mechanism between containers and external systems.

**Multi-Stage Build** → Technique for creating optimized production images.
