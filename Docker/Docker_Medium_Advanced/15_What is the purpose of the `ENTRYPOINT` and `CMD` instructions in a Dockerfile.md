15. **What is the purpose of the `ENTRYPOINT` and `CMD` instructions in a Dockerfile?**

### Short Answer:
In a Dockerfile, `ENTRYPOINT` specifies the main command to run when a container starts, while `CMD` provides default arguments for that command. If both are defined, `CMD` will be used as arguments to the `ENTRYPOINT`. 

**Example:**
```dockerfile
ENTRYPOINT ["python", "app.py"]
CMD ["--port", "8080"]
```
This runs `python app.py --port 8080` when the container starts.

### Detailed Answer:
In Docker, the `ENTRYPOINT` and `CMD` instructions serve different purposes but can work together to define the behavior of a container.

1. **`ENTRYPOINT`:**
   - Defines the **main command** that is always executed when the container starts.
   - It is not overridden by any command-line arguments passed when running the container.
   - Can be set in two forms:
     - **Exec form** (preferred, as it avoids invoking a shell): `ENTRYPOINT ["executable", "param1", "param2"]`
     - **Shell form** (which runs the command via `/bin/sh -c`): `ENTRYPOINT command param1 param2`

2. **`CMD`:**
   - Specifies the **default arguments** to the command in `ENTRYPOINT`.
   - If arguments are provided when running the container, they override the `CMD` values.
   - `CMD` can also be used independently, setting the full command if `ENTRYPOINT` is not used.

**Combined Usage Example:**
```dockerfile
ENTRYPOINT ["python", "app.py"]
CMD ["--host", "0.0.0.0", "--port", "8080"]
```
- **How it works**: When the container is run, `python app.py --host 0.0.0.0 --port 8080` will be executed. If you pass additional arguments like `python app.py --host 127.0.0.1`, the CMD arguments (`--host 0.0.0.0 --port 8080`) are replaced.

### Key Takeaway:
- `ENTRYPOINT` is the main executable for the container.
- `CMD` is used for providing default arguments, which can be overridden at runtime.