# 🐳 Docker Commands Cheat Sheet

This document contains the most commonly used Docker commands for day-to-day development, troubleshooting, and interview preparation.

> 💡 **Note:** This is a quick revision guide, not a Docker tutorial. Each command includes a simple purpose so you can quickly recall when to use it.

---

# 📦 Container Commands

| Command | Purpose |
|---------|---------|
| `docker run <image>` | Create and start a new container from an image. |
| `docker run -d <image>` | Run a container in the background (Detached Mode). |
| `docker run -it <image> sh` | Start a container in interactive mode. |
| `docker run -p HOST:CONTAINER <image>` | Map a container port to the host. |
| `docker run -P <image>` | Automatically map all exposed ports to random host ports. |
| `docker run --name <name> <image>` | Start a container with a custom name. |
| `docker run --network <network> <image>` | Start a container on a specific Docker network. |
| `docker run -v <volume>:<path> <image>` | Mount a Docker Volume into the container. |
| `docker ps` | List all running containers. |
| `docker ps -a` | List all containers, including stopped ones. |
| `docker stop <container>` | Stop a running container. |
| `docker start <container>` | Start a stopped container. |
| `docker restart <container>` | Restart a container. |
| `docker pause <container>` | Pause all processes inside a container. |
| `docker unpause <container>` | Resume a paused container. |
| `docker rm <container>` | Remove a stopped container. |
| `docker rm -f <container>` | Force remove a running container. |
| `docker rm -f $(docker ps -q)` | Remove all running containers. |
| `docker rm -f $(docker ps -aq)` | Remove all containers. |
| `docker rename <old> <new>` | Rename a container. |
| `docker exec -it <container> sh` | Open an interactive shell inside a running container. |
| `docker attach <container>` | Attach your terminal to a running container. |
| `docker logs <container>` | View container logs. |
| `docker logs -f <container>` | Follow logs in real time. |
| `docker inspect <container>` | View detailed container configuration. |
| `docker stats` | Display live CPU, memory, and network usage. |
| `docker top <container>` | Show running processes inside a container. |
| `docker wait <container>` | Wait until a container stops and return its exit code. |

# 🖼️ Image Commands

| Command | Purpose |
|---------|---------|
| `docker images` | List all Docker Images available on your system. |
| `docker image ls` | Another way to list Docker Images. |
| `docker pull <image>` | Download an image from Docker Hub or another registry. |
| `docker build -t <image>:<tag> .` | Build a Docker Image from a Dockerfile. |
| `docker build --no-cache -t <image> .` | Build an image without using cached layers. |
| `docker tag <source-image> <username/repository:tag>` | Create a new tag for an existing image. |
| `docker push <username/repository:tag>` | Push an image to a Docker Registry. |
| `docker rmi <image>` | Remove a Docker Image. |
| `docker rmi -f <image>` | Force remove a Docker Image. |
| `docker history <image>` | View the layer history of an image. |
| `docker image inspect <image>` | Display detailed information about an image. |
| `docker save -o <file>.tar <image>` | Save a Docker Image as a tar file. |
| `docker load -i <file>.tar` | Load a Docker Image from a tar file. |

---

### 💻 Examples

```bash
# Download an image
docker pull nginx

# Build an image
docker build -t my-app:v1 .

# Tag an image
docker tag my-app:v1 mayurwarungase/my-app:v1

# Push an image
docker push mayurwarungase/my-app:v1

# Save an image
docker save -o nginx.tar nginx

# Load an image
docker load -i nginx.tar
```

# 💾 Volume Commands

| Command | Purpose |
|---------|---------|
| `docker volume create <volume>` | Create a new Docker Volume. |
| `docker volume ls` | List all Docker Volumes. |
| `docker volume inspect <volume>` | View detailed information about a Docker Volume. |
| `docker volume rm <volume>` | Remove a Docker Volume. |
| `docker volume prune` | Remove all unused Docker Volumes. |

---

### 💻 Examples

```bash
# Create a volume
docker volume create my-volume

# List all volumes
docker volume ls

# Mount a volume
docker run -d -v my-volume:/usr/share/nginx/html nginx

# Inspect a volume
docker volume inspect my-volume

# Remove unused volumes
docker volume prune
```

---
