16. **How do you troubleshoot a failed container?**

### Short Answer:
To troubleshoot a failed container, you can:

1. **Check container logs** using `docker logs <container_id>` to view the error messages.
2. **Inspect container status** with `docker ps -a` to see if it's stopped or exited, and check for the exit code.
3. **Use `docker inspect`** to gather detailed information about the container's configuration and environment.
4. **Connect to the container** using `docker exec -it <container_id> /bin/bash` to inspect the file system and diagnose the issue interactively.

---

### Detailed Answer:
When a container fails to start or stops unexpectedly, follow these troubleshooting steps:

1. **Check the logs**: Run `docker logs <container_id>` to check the logs for any error messages or stack traces that could provide insight into why the container failed.

2. **Inspect the container status**: Use `docker ps -a` to list all containers, including stopped ones. This will show the status of your container. Look for exit codes (e.g., `Exit 1`), which can indicate issues like misconfiguration or missing dependencies.

3. **Inspect container details**: Use `docker inspect <container_id>` to get detailed information about the container’s configuration, network settings, and environment variables. This can help identify any misconfigurations or issues with the container setup.

4. **Access the container's shell**: If needed, connect to the container's shell using `docker exec -it <container_id> /bin/bash` (or `/bin/sh` for lightweight images) to examine the file system and configuration files directly. This allows you to interact with the container and perform manual diagnostics.

By following these steps, you can systematically identify and resolve the cause of a container failure.