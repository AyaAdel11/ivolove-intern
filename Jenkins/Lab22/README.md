# Lab 22: End-to-End CI/CD Pipeline with Jenkins & Kubernetes (Minikube)

## 🎯 Project Overview
This lab demonstrates a complete CI/CD automation workflow. The pipeline builds a Spring Boot application, packages it into a Docker image, pushes it to Docker Hub, and finally deploys it to a local Kubernetes cluster (Minikube).

## 🏗️ Architecture
1.  **Source Control:** GitHub (Triggers Jenkins Build).
2.  **CI Tool:** Jenkins (Automates the entire process).
3.  **Containerization:** Docker (Builds and tags images based on build numbers).
4.  **Orchestration:** Kubernetes (Minikube) (Hosts the running application).

---

## 🚀 Pipeline Stages

1.  **Checkout:** Pulls the latest code from the GitHub repository.
2.  **Docker Build:** Builds a new Docker image tagged with `${env.BUILD_NUMBER}`.
3.  **Docker Push:** Authenticates and pushes the image to Docker Hub (`AyaAdel11/jenkins-app`).
4.  **Update Deployment:** Uses `sed` to dynamically update the `deployment.yaml` with the new image tag.
5.  **K8s Deploy:** Deploys the application using `kubectl apply` to the Minikube cluster.
6.  **Cleanup:** Removes local Docker images to save disk space.

---

## 🛠️ Key Commands Used

### 1. Jenkins to K8s Configuration
To allow Jenkins to communicate with Minikube, we mapped the kubeconfig and certificates:
```bash
sudo mkdir -p /var/lib/jenkins/.kube
sudo cp ~/.kube/config /var/lib/jenkins/.kube/config
sudo cp -r ~/.minikube /var/lib/jenkins/
sudo chown -R jenkins:jenkins /var/lib/jenkins/.kube
sudo chown -R jenkins:jenkins /var/lib/jenkins/.minikube
# Update paths in config
sudo sed -i 's|/home/aya|/var/lib/jenkins|g' /var/lib/jenkins/.kube/config
```
### 2. Deployment Command
Inside the Jenkinsfile, the deployment is executed as:

```bash
sh "kubectl --kubeconfig=/var/lib/jenkins/.kube/config apply -f deployment.yaml --validate=false"
```

## 📦 Kubernetes Objects
Deployment: Manages 2 replicas of the application pod.

Service: Exposed via NodePort to allow external access to the app on port 8080.

## Challenges & Solutions
Permission Denied (Certs): Fixed by copying .minikube certificates to the jenkins home directory and updating the kubeconfig paths.

Connection Refused: Resolved by ensuring minikube start --driver=docker was running and refreshing the kubeconfig with the new API server port.

Dynamic Tagging: Used sed to automate image versioning, ensuring the cluster always runs the latest build.

## 🖼️ Pipeline Execution
![Pipeline Status](./pipeline.png)
