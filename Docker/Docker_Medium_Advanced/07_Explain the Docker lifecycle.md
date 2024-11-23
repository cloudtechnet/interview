7.Explain the Docker lifecycle?

### **Short Answer:**

The Docker container lifecycle includes:  
1. **Creating** - Container is created from an image but not running.  
2. **Starting** - Starts a stopped container.  
3. **Pausing** - Suspends a running container.  
4. **Stopping** - Gracefully stops a running container.  
5. **Restarting** - Stops and starts a container.  
6. **Removing** - Deletes a stopped container.  

This sequence describes how containers are managed in Docker during their lifecycle.  

---

### **Detailed Answer:**

1. **Creating**:  
   A container is created from an image using the `docker create` command or implicitly with `docker run`. At this stage, the container exists but is not running.  
   Example:  
   ```bash
   docker create --name my-container nginx
   ```

2. **Starting**:  
   A stopped or newly created container is started using the `docker start` command. This transitions the container to a running state.  
   Example:  
   ```bash
   docker start my-container
   ```

3. **Pausing**:  
   A running container can be paused using `docker pause`, which suspends its processes (e.g., useful for maintenance).  
   Example:  
   ```bash
   docker pause my-container
   ```

4. **Stopping**:  
   Gracefully stops a running container using `docker stop`. It allows the container to clean up resources before shutting down.  
   Example:  
   ```bash
   docker stop my-container
   ```

5. **Restarting**:  
   A container can be restarted using `docker restart`. This stops and starts it in one command.  
   Example:  
   ```bash
   docker restart my-container
   ```

6. **Removing**:  
   A stopped container can be removed using `docker rm`. This clears the container from the system, but it does not delete the image.  
   Example:  
   ```bash
   docker rm my-container
   ```

These stages ensure containers are efficiently managed across development, testing, and production environments.