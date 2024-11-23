20. **Explain the difference between `docker run` and `docker start`.**

**Short Answer:**

- `docker run` creates and starts a new container from an image.
- `docker start` restarts an existing container that is currently stopped.

---

**Detailed Answer:**

- **`docker run`** is used to create a new container from a specified image and immediately start it. When you run this command, Docker pulls the image (if not already available locally), sets up the container, and then starts its execution.
  
  Example:  
  ```bash
  docker run -d --name my-container nginx
  ```
  This command creates a new container named `my-container` from the `nginx` image and runs it in detached mode.

- **`docker start`** is used to restart a previously created and stopped container. This command does not create a new container; it only starts a container that was previously created but has stopped.
  
  Example:  
  ```bash
  docker start my-container
  ```
  This command restarts the container named `my-container` that was previously stopped.

In short, `docker run` is for creating and running new containers, while `docker start` is for restarting existing ones that are in a stopped state.