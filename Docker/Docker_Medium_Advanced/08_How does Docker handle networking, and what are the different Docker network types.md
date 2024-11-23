8.How does Docker handle networking, and what are the different Docker network types?

### **Short Answer**  
Common Docker security vulnerabilities include:  
1. **Running containers as root**: Mitigate by enabling user namespaces and using non-root users.  
2. **Using untrusted images**: Always use trusted, verified images from official repositories.  
3. **Exposing unnecessary ports**: Limit exposed ports and use firewalls to restrict access.  
4. **Not updating images**: Regularly update and scan images for vulnerabilities using tools like Trivy or Clair.  
Mitigating these involves applying the principle of least privilege, using minimal base images, automating image scans, and configuring secure networking.

---

### **Detailed Answer**  

1. **Running containers as root**  
   - **Vulnerability**: Containers running with root privileges can be exploited to access the host system.  
   - **Mitigation**:  
     - Use the `--user` flag to run containers with non-root users.  
     - Enable **user namespaces** to map container users to non-root users on the host.  
     - Ensure your Dockerfiles include `USER` directives for applications that don't need root access.  

2. **Using untrusted or bloated images**  
   - **Vulnerability**: Using images from unverified sources or bloated images with unnecessary libraries increases attack surface.  
   - **Mitigation**:  
     - Use images from trusted sources like Docker Hub (official images) or private registries.  
     - Prefer minimal base images like `alpine` to reduce attack vectors.  
     - Use tools like Docker Content Trust (DCT) to verify image signatures.  

3. **Exposing unnecessary ports**  
   - **Vulnerability**: Exposing multiple or unused ports allows attackers to exploit open services.  
   - **Mitigation**:  
     - Only expose ports required for application functionality (`-p` or `--expose`).  
     - Use a firewall (e.g., iptables or Docker’s network policies) to restrict access.  
     - Consider running services on private networks within the Docker environment.  

4. **Not updating or scanning images**  
   - **Vulnerability**: Outdated images may have known vulnerabilities.  
   - **Mitigation**:  
     - Regularly pull updated versions of base and application images.  
     - Automate scanning of images with tools like **Trivy**, **Aqua Security**, or **Clair** during the CI/CD pipeline.  

5. **General Best Practices**:  
   - Use **read-only file systems** (`--read-only`) for containers that don’t need write access.  
   - Apply the **principle of least privilege** for container permissions.  
   - Leverage tools like **AppArmor** or **SELinux** for runtime security policies.  
   - Monitor container runtime activity using tools like Falco for detecting unusual behaviors.  

By demonstrating awareness of vulnerabilities and actionable mitigations, you'll show strong practical knowledge during the interview.
 