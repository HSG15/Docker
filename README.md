# 🐳 Commonly Used Docker Commands (Cheat Sheet)

This README contains the **most commonly used Docker commands** with simple explanations, all in tabular format.

---

## 📋 Docker Commands Table

| Category                | Command Example                                         | Explanation                                                                 |
|--------------------------|---------------------------------------------------------|-----------------------------------------------------------------------------|
| **Check Installation**   | `docker`                                               | Lists available Docker commands.                                            |
|                          | `docker -v`                                            | Shows installed Docker version.                                             |
| **Images**               | `docker pull <image-name>`                             | Downloads an image from Docker Hub (e.g., `docker pull nginx`).             |
|                          | `docker images`                                        | Lists all downloaded images on your system.                                 |
|                          | `docker inspect <image-name>`                          | Shows detailed info (metadata) about an image.                              |
| **Containers (Run)**     | `docker run <image-name>`                              | Creates and runs a new container from an image.                             |
|                          | `docker run -it <image-name>`                          | Runs container in **interactive mode** (gives you shell access).            |
|                          | `docker run -d <image-name>`                           | Runs container in **detached mode** (background).                           |
| **View Containers**      | `docker ps -a`                                         | Shows **all containers** (running + stopped).                               |
|                          | `docker container ls`                                  | Shows only **running containers**.                                          |
|                          | `docker inspect <container-id>`                        | Shows detailed info about a container.                                      |
|                          | `docker top <container-id>`                            | Displays processes running inside a container.                              |
| **Start/Stop**           | `docker start <container-id>`                          | Starts an existing container.                                               |
|                          | `docker stop <container-id>`                           | Stops a running container.                                                  |
|                          | `docker restart <container-id>`                        | Restarts a container.                                                       |
|                          | `docker pause <container-id>`                          | Pauses all processes in a container.                                        |
|                          | `docker unpause <container-id>`                        | Resumes a paused container.                                                 |
| **Remove**               | `docker rm <container-id>`                             | Removes a stopped container.                                                |
|                          | `docker rmi <image-name>`                              | Removes an image (⚠️ fails if containers depend on it).                      |
|                          | `docker system prune`                                  | Cleans up unused containers, images, and networks.                          |
| **Port Binding**         | `docker run -p <host-port>:<container-port> <image>`   | Maps container ports to host ports.                                         |
|                          | `docker run -p 8080:3306 hello-world`                  | Example → Maps container’s port `3306` to host’s port `8080`.               |
| **Logs & Debugging**     | `docker logs <container-name>`                         | Shows logs of a container.                                                  |
|                          | `docker logs -f <container-name>`                      | Follows (streams) container logs.                                           |
|                          | `docker exec -it <container-id> /bin/bash`             | Opens an interactive shell inside a running container.                      |
| **Copy Files**           | `docker cp <host-path> <container-id>:<container-path>`| Copies file **from host → container**.                                      |
|                          | `docker cp <container-id>:<container-path> <host-path>`| Copies file **from container → host**.                                      |
| **Volumes (Persistence)**| `docker volume ls`                                     | Lists all volumes.                                                          |
|                          | `docker volume inspect <volume-name>`                  | Shows volume details.                                                       |
|                          | `docker run -v mydata:/app/data <image>`               | Mounts a named volume inside a container.                                   |
| **Networks**             | `docker network ls`                                    | Lists available Docker networks.                                            |
|                          | `docker network inspect <network-name>`                | Shows details of a Docker network.                                          |
|                          | `docker network create <network-name>`                 | Creates a custom network.                                                   |
| **Stats & Monitoring**   | `docker stats`                                         | Real-time stats of running containers (CPU, memory, network, etc.).         |
|                          | `docker events`                                        | Streams Docker events in real-time.                                         |
| **Build & Push**         | `docker build -t myapp:1.0 .`                          | Builds an image from a Dockerfile in current directory.                      |
|                          | `docker tag myapp:1.0 myrepo/myapp:1.0`                | Tags an image for pushing to Docker Hub.                                    |
|                          | `docker push myrepo/myapp:1.0`                         | Pushes image to Docker Hub.                                                 |
| **System Info**          | `docker info`                                          | Shows detailed system-wide Docker info.                                     |
|                          | `docker version`                                       | Shows client & server Docker versions.                                      |

---

✅ **Summary:**  
- **Image → Container** is like **Blueprint → House**.  
- Daily workflow: `docker pull`, `docker run`, `docker ps`, `docker stop`, `docker rm`.  
- Use `docker exec` for interactive shell, `docker logs -f` for debugging.  
- Clean up with `docker system prune` regularly.  
- For multi-container apps → use **Docker Compose**.  
