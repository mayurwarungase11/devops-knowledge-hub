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

---
