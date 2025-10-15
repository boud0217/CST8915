# Lab 4
Video link : [Demo Video](https://youtu.be/5hJLHE_juik)

## What are the main differences between a Docker image and a Docker container?
A Docker image is a lightweight, standalone, and executable software package that includes everything needed to run a piece of software, including the code, runtime, libraries, environment variables, and configuration files. It is a read-only template used to create Docker containers.
A Docker container, on the other hand, is a runtime instance of a Docker image. It is a lightweight, portable, and self-sufficient environment that runs the application defined by the image. Containers are isolated from each other and the host system, but they share the same OS kernel.

## Explain how Docker's layered architecture improves efficiency
Docker's layered architecture improves efficiency in several ways:
1. Reusability: Layers can be reused across different images. If multiple images share the same base layer, Docker only needs to store that layer once, saving disk space.
2. Caching: When building images, Docker caches each layer. If a layer hasn't changed, Docker can reuse the cached version, speeding up the build process.
3. Incremental Updates: When an image is updated, only the layers that have changed need to be downloaded or transferred, reducing bandwidth usage and speeding up deployment.

## Why does each container get its own writable layer?
Each container gets its own writable layer to allow for isolation and customization of the container's filesystem. This writable layer enables the container to make changes, such as creating, modifying, or deleting files, without affecting the underlying image or other containers that may be using the same image. This separation ensures that each container can operate independently and maintain its own state while still benefiting from the shared layers of the base image.

## What are the benefits of using Docker Compose over running containers individually?
Docker Compose offers several benefits over running containers individually:
1. Simplified Configuration: Docker Compose allows you to define multi-container applications in a single YAML file, making it easier to manage and configure complex setups.
2. Easier Orchestration: With Docker Compose, you can start, stop, and manage multiple containers with a single command, simplifying the orchestration of services.
3. Consistency: Docker Compose ensures that the same configuration is used across different environments (development, testing, production), reducing the chances of discrepancies.
4. Networking: Docker Compose automatically creates a network for the containers defined in the compose file, allowing them to communicate with each other easily.
5. Volume Management: Docker Compose simplifies the management of data volumes, allowing you to define and share volumes between containers easily.
