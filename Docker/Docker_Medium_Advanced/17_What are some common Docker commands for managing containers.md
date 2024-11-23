17.What are some common Docker commands for managing containers?

**Short Answer**:  
Common Docker commands for managing containers include:
- `docker run`: Starts a new container from an image.
- `docker ps`: Lists running containers.
- `docker stop`: Stops a running container.
- `docker rm`: Removes a stopped container.
- `docker exec`: Executes a command inside a running container.

---

**Detailed Answer**:

In a DevOps interview, you can elaborate on these commands with practical use cases:

1. **`docker run`**  
   This command is used to create and start a container from a specified Docker image.  
   Example:  
   ```bash
   docker run -d -p 80:80 nginx
   ```
   This runs an Nginx container in detached mode (`-d`) and maps port 80 of the host to port 80 of the container.

2. **`docker ps`**  
   Lists all running containers.  
   Example:  
   ```bash
   docker ps
   ```
   This shows active containers with information such as container ID, names, and ports.

3. **`docker stop`**  
   Stops a running container gracefully.  
   Example:  
   ```bash
   docker stop <container_id>
   ```
   This will stop the specified container without removing it.

4. **`docker rm`**  
   Removes a stopped container from the system.  
   Example:  
   ```bash
   docker rm <container_id>
   ```
   After stopping a container, you can remove it to free up resources.

5. **`docker exec`**  
   Runs a command inside a running container.  
   Example:  
   ```bash
   docker exec -it <container_id> bash
   ```
   This opens an interactive terminal (`-it`) inside the container to execute commands like `bash`.

These commands form the foundation of Docker container management, helping in creating, monitoring, stopping, and interacting with containers.