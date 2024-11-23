5.Can you explain the role of `docker-compose`?

### **Short Answer:**
`docker-compose` is a tool used in DevOps to define, manage, and run multi-container Docker applications. It allows you to use a simple YAML file to configure all your application services, networks, and volumes, making it easy to start, stop, and link multiple containers with a single command.

---

### **Detailed Answer:**
`docker-compose` is a command-line tool that simplifies the process of running and managing multi-container Docker applications. It allows you to define your application’s services, networks, and volumes in a single `docker-compose.yml` file. This makes it easier to handle complex setups where multiple containers need to interact, such as a web application with separate containers for the frontend, backend, and database.

Key benefits of `docker-compose`:
1. **Centralized Configuration**: All services and dependencies are defined in one YAML file.
2. **Service Linking**: Automatically links containers and allows them to communicate over a private network.
3. **Ease of Scaling**: You can scale services up or down using a simple command.
4. **Multi-Environment Support**: Supports different configurations for development, testing, and production.
5. **Simplified Commands**: Commands like `docker-compose up` and `docker-compose down` make managing services easy.

In a DevOps workflow, `docker-compose` is particularly useful for local development, testing, and CI/CD pipelines. It ensures consistency across environments and reduces the complexity of managing individual containers manually.