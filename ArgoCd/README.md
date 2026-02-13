# Lab 25: GitOps Implementation with Jenkins & ArgoCD
## 📌 Project Overview
This lab demonstrates a full GitOps lifecycle for a containerized application. We transitioned from traditional CI/CD to a GitOps model where Git acts as the single source of truth. The pipeline automates building, pushing, and updating Kubernetes manifests, while ArgoCD ensures the cluster state matches the Git repository.

## 🏗️ Architecture
The workflow follows these stages:

Continuous Integration (CI): Jenkins builds the Docker image and pushes it to Docker Hub.

Manifest Update: Jenkins updates the deployment.yaml file in the GitHub repository with the new image tag.

Continuous Deployment (CD): ArgoCD detects the change in GitHub and automatically synchronizes the state to the Minikube cluster.

## 🛠️ Prerequisites & Setup
Minikube: Allocated with 1800MB RAM for stability.

Jenkins: Configured with Docker Hub and GitHub credentials.

ArgoCD: Installed in a dedicated namespace argocd.

Port-Forwarding: Used to access ArgoCD UI:

```bash
kubectl port-forward svc/argocd-server -n argocd 9090:443
```

## 📝 Configuration Details
### 1. Jenkins Pipeline (Jenkinsfile)
The pipeline includes a stage to update the Git repository:

```bash 
stage('Update Git Manifest') {
    steps {
        withCredentials([usernamePassword(credentialsId: 'github', passwordVariable: 'GIT_PASS', usernameVariable: 'GIT_USER')]) {
            sh """
                sed -i 's|image: .*|image: ${DOCKER_USER}/${APP_NAME}:1.0.0-${BUILD_NUMBER}|' deployment.yaml
                git add deployment.yaml
                git commit -m "Update deployment.yaml with image tag 1.0.0-${BUILD_NUMBER}"
                git push https://${GIT_USER}:${GIT_PASS}@github.com/${GIT_USER}/Jenkins-app.git main
            """
        }
    }
}
```

### 2. ArgoCD Application Settings
Sync Policy: Automatic

Self-Heal: Enabled (to prevent configuration drift).

Prune Resources: Enabled (to remove old objects).

## 🚀 Deployment Results
Image Repository: ayaadel02/jenkins-app

ArgoCD Status: * Health: Healthy 🟢

Sync Status: Synced ✅

Kubernetes Pods: Successfully transitioned from ImagePullBackOff to Running after fixing the image naming convention.

## 💡 Key Learnings
Automated Sync: How ArgoCD monitors Git changes without manual intervention.

Rolling Updates: Kubernetes manages the transition between old and new pods to ensure zero downtime.

Troubleshooting: Identifying image pull errors using kubectl describe and fixing manifest mismatches.

How to run the application locally?
After deployment, run the following to access the app:

```Bash
kubectl port-forward svc/jenkins-app-service 5000:80
```

Then visit: http://localhost:5000


![Task Proof](./screenshots/pods.png)
![Task Proof](./screenshots/argocd.png)
![Task Proof](./screenshots/app.png)
