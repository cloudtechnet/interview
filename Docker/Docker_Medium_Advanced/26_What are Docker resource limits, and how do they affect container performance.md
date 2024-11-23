26_What are Docker resource limits, and how do they affect container performance?

### Short Answer:
Docker resource limits, such as `--memory` and `--cpu`, allow you to restrict the amount of resources a container can use, ensuring it doesn't over-consume host resources. These limits are enforced using cgroups, a Linux kernel feature that allocates and controls resource usage. Setting appropriate limits helps prevent resource starvation on the host and ensures stable performance for other containers.

---

### Detailed Answer:
In Docker, resource limits are used to control how much CPU and memory a container can access, preventing a container from consuming excessive resources and affecting the performance of other containers or the host system itself. The two main resource limits you can set are:

- **`--memory`**: Limits the maximum amount of memory a container can use. If the container exceeds this limit, it will be terminated (OOM – Out of Memory).
- **`--cpu`**: Specifies how much CPU time a container can use. This can be controlled by limiting the number of CPU cores or setting the CPU shares, which adjusts the container's access to CPU time relative to other containers.

These limits are enforced by **cgroups** (control groups), a Linux kernel feature that manages and limits the resource usage of processes. Cgroups ensure that each container gets its fair share of resources without starving the host system or other containers.

Setting appropriate resource limits is crucial in production environments. Without limits, a poorly behaving container could consume all available memory or CPU, causing other containers or the host system to become unresponsive. By defining these limits, you help maintain system stability, ensure fair resource allocation, and prevent performance degradation caused by resource contention.