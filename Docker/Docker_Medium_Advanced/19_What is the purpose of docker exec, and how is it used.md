19.What is the purpose of `docker exec`, and how is it used?

### Short Answer:
`docker exec` is used to run commands inside a running container. It is commonly used to start an interactive terminal session or execute specific commands for debugging and troubleshooting purposes. For example, `docker exec -it <container_id> /bin/bash` opens an interactive shell inside the container.

### Detailed Answer:
`docker exec` allows you to execute commands in an already running Docker container. This is useful for debugging, inspecting logs, or making changes to a running container without stopping it. It supports both non-interactive commands and interactive sessions.

For example:
- **Interactive Terminal**: `docker exec -it <container_id> /bin/bash` opens a bash shell inside the container, allowing you to interact with it directly.
- **Execute Commands**: You can run a one-off command, such as `docker exec <container_id> ls /app`, to list files in a specific directory.

It’s commonly used in DevOps for debugging and maintenance without interrupting the container’s normal operations.
