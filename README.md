# Ivolve Intern - DevOps Labs Portfolio

This repository contains my comprehensive progress during the DevOps internship, covering Build Tools, Dockerization, and Advanced Kubernetes Orchestration.

## 🛠️ Build Tools & Containerization
1. **[Lab 1: Gradle Project](./Gradle/README.md)** - Building Java apps with Gradle.
2. **[Lab 2: Maven Project](./Maven/README.md)** - Building and Packaging with Maven.
3. **[Lab 3: Dockerized Spring Boot App](./Docker/Lab3/README.md)** - Running Java applications in Containers.
4. **[Lab 4: Optimized Containerization](./Docker/Lab4/README.md)** - Single-stage builds using lightweight Java runtime images.
5. **[Lab 5: Multi-Stage Build Strategy](./Docker/Lab5/README.md)** - Professional Docker optimization for production-ready Spring Boot apps.
6. **[Lab 6: Managing Docker Environment Variables](./Docker/Lab6/README.md)** - Managing Docker Environment Variables.
7. **[Lab 7: Docker Volume and Bind Mount with Nginx](./Docker/Lab7/README.md)** - Persistent data and configuration mounting in Docker.
8. **[Lab 8: Docker Networking & Inter-Container Communication](./Docker/Lab8/README.md)** - Connecting multiple containers in a dedicated bridge network.
9. **[Lab 9: Containerized Node.js and MySQL Stack](./Docker/Lab9/README.md)** - Full-stack orchestration with persistence and health checks using Docker Compose.

## ☸️ Kubernetes (Orchestration & Administration)
10. **[Lab 10: Node Isolation Using Taints](./K8s/Lab10/README.md)** - Controlling pod scheduling and isolating nodes using Taints and Tolerations.
11. **[Lab 11: Namespace Management & Resource Quotas](./K8s/Lab11/README.md)** - Implementing multi-tenancy and enforcing resource limits.
12. **[Lab 12: Configuration & Secret Management](./K8s/Lab12/README.md)** - Decoupling configuration (ConfigMaps) and sensitive data (Secrets) from code.
13. **[Lab 13: Persistent Storage Setup](./K8s/Lab13/README.md)** - Configuring Persistent Volumes (PV) and Claims (PVC) for application logging.
14. **[Lab 14: StatefulSet with Headless Service](./K8s/Lab14/README.md)** - Deploying stateful applications (MySQL) with stable network identities and storage.
15. **[Lab 15: Node.js App Deployment & ClusterIP](./K8s/Lab15/README.md)** - Scaling applications and exposing them internally via ClusterIP services.
16. **[Lab 16: Init Containers for DB Setup](./K8s/Lab16/README.md)** - Automating database initialization and user privileges using Init Containers.
17. **[Lab 17: Resource Requests and Limits](./K8s/Lab17/README.md)** - Optimizing pod performance and stability using CPU/Memory constraints.
18. **[Lab 18: Pod-to-Pod Traffic Control](./K8s/Lab18/README.md)** - Securing network communication between services using Network Policies.
19. **[Lab 19: DaemonSets for Monitoring](./K8s/Lab19/README.md)** - Deploying node-level agents (Prometheus Node Exporter) across the entire cluster.
20. **[Lab 20: RBAC & Service Accounts](./K8s/Lab20/README.md)** - Implementing Role-Based Access Control to secure cluster resources.

## Continues Integration / Continues Delivery
21. **[Lab 21: Role-Based Authorization](./Jenkins/Lab21/README.md)** - Implementing RBAC with Admin and Read-only roles in Jenkins.
22. **[Lab 22: CI/CD Pipeline for App Deployment](./Jenkins/Lab22/README.md)** - Automating Build, Dockerization, and K8s deployment with Pipeline post-actions.
23. **[Lab 23: Jenkins Shared Libraries & Agents](./Jenkins/Lab23/README.md)** - Scaling pipelines using modular Shared Libraries and distributed Jenkins Slaves.
24. **[ Lab 24: Multi-branch CI/CD Workflow](./Jenkins/Lab24/README.md)** - Automated environment-based deployment (Dev/Staging/Prod) using Multibranch Pipelines.

## GitOps with ArgoCD
Lab 25: GitOps Workflow with ArgoCD - Implementing continuous delivery by synchronizing K8s cluster state with GitHub via ArgoCD.

## Ansible Automation 
Lab 26: Ansible Configuration & Ad-Hoc - Control node setup, SSH key management, and executing ad-hoc commands.
Lab 27: Web Server Automation - Writing playbooks to automate Nginx installation and configuration.
Lab 28: Configuration Management with Roles - Creating structured roles for Docker, Kubectl, and Jenkins installation.
Lab 29: Ansible Vault & Database Automation - Automating MySQL setup and securing sensitive credentials with Ansible Vault.
Lab 30: Dynamic Inventory with AWS - Automated host discovery for EC2 instances using Dynamic Inventory and AWS tags.
