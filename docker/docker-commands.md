# 🐳 Docker Commands Cheat Sheet

This document contains the most commonly used Docker commands for day-to-day development, troubleshooting, and interview preparation.

> 💡 **Note:** This is a quick revision guide, not a Docker tutorial. Each command includes a simple purpose so you can quickly recall when to use it.

---
## 📚 Contents

- Container Commands
- Image Commands
- Volume Commands
- Network Commands
- Docker Compose Commands
- Registry Commands
- Inspection & Troubleshooting Commands
- Cleanup Commands

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

# 🌐 Network Commands

| Command | Purpose |
|---------|---------|
| `docker network ls` | List all Docker Networks. |
| `docker network create <network>` | Create a new Docker Network. |
| `docker network create --subnet <subnet> <network>` | Create a network with a custom subnet. |
| `docker network inspect <network>` | Display detailed information about a Docker Network. |
| `docker network connect <network> <container>` | Connect a running container to a network. |
| `docker network disconnect <network> <container>` | Disconnect a container from a network. |
| `docker network rm <network>` | Remove a Docker Network. |
| `docker network prune` | Remove all unused Docker Networks. |

---

### 💻 Examples

```bash
# Create a network
docker network create my-network

# Create a network with subnet
docker network create --subnet 172.18.0.0/20 my-network

# Run a container on a network
docker run -d --network my-network nginx

# Inspect a network
docker network inspect my-network

# Remove unused networks
docker network prune
```

# 🐳 Docker Compose Commands

| Command | Purpose |
|---------|---------|
| `docker compose up` | Create and start all services defined in the Compose file. |
| `docker compose up -d` | Start all services in the background (Detached Mode). |
| `docker compose down` | Stop and remove all services, networks, and containers created by Compose. |
| `docker compose ps` | List all services and their current status. |
| `docker compose logs` | View logs from all Compose services. |
| `docker compose logs -f` | Follow logs in real time. |
| `docker compose build` | Build or rebuild service images. |
| `docker compose restart` | Restart one or more services. |
| `docker compose stop` | Stop services without removing them. |
| `docker compose start` | Start previously stopped services. |

---

### 💻 Examples

```bash
# Start all services
docker compose up -d

# View running services
docker compose ps

# View logs
docker compose logs -f

# Stop and remove everything
docker compose down
```

# 📦 Registry Commands

| Command | Purpose |
|---------|---------|
| `docker login` | Log in to a Docker Registry. |
| `docker logout` | Log out from the current Docker Registry. |
| `docker tag <image> <username/repository:tag>` | Create a new tag before pushing an image. |
| `docker push <username/repository:tag>` | Upload an image to a Docker Registry. |
| `docker pull <image>` | Download an image from a Docker Registry. |

---

### 💻 Examples

```bash
# Login
docker login

# Tag an image
docker tag my-app:v1 mayurwarungase/my-app:v1

# Push an image
docker push mayurwarungase/my-app:v1

# Pull an image
docker pull nginx
```

# 🔍 Inspection & Troubleshooting Commands

| Command | Purpose |
|---------|---------|
| `docker logs <container>` | View container logs. |
| `docker logs -f <container>` | Follow container logs in real time. |
| `docker exec -it <container> sh` | Open an interactive shell inside a running container. |
| `docker inspect <container>` | Display detailed container information. |
| `docker top <container>` | Show running processes inside a container. |
| `docker stats` | Display live CPU, memory, and network usage. |
| `docker events` | Monitor Docker events in real time. |
| `docker diff <container>` | Show changes made to a container's filesystem. |
| `docker system df` | Display Docker disk usage. |
| `docker version` | Display Docker Client and Server version information. |
| `docker info` | Display detailed Docker system information. |

---

### 💻 Examples

```bash
# View logs
docker logs my-app

# Access a container
docker exec -it my-app sh

# View Docker disk usage
docker system df

# View Docker information
docker info
```

# 🧹 Cleanup Commands

| Command | Purpose |
|---------|---------|
| `docker system prune` | Remove unused Docker resources. |
| `docker system prune -a` | Remove all unused images, containers, networks, and build cache. |
| `docker system prune --volumes` | Remove unused Docker Volumes along with other unused resources. |
| `docker image prune` | Remove unused (dangling) Docker Images. |
| `docker container prune` | Remove all stopped containers. |
| `docker volume prune` | Remove all unused Docker Volumes. |
| `docker network prune` | Remove all unused Docker Networks. |

---

### 💻 Examples

```bash
# Check Docker disk usage
docker system df

# Remove unused Docker resources
docker system prune

# Remove stopped containers
docker container prune

# Remove unused volumes
docker volume prune
```

---

> 💡 **Quick Note:** Always review what you're deleting before using cleanup commands in production. Volumes may contain persistent application data, so avoid deleting them unless you're sure they're no longer needed.

## 💡 Interview Tips

- Learn commands by category instead of memorizing them randomly.
- Practice the commands in a local Docker environment.
- Understand what each command does before memorizing its syntax.
- For troubleshooting, remember the workflow:
  1. `docker ps`
  2. `docker logs`
  3. `docker inspect`
  4. `docker exec`
  5. Find the root cause.
