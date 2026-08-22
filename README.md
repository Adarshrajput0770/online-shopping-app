# 🛒 Online Shopping App - DevOps CI/CD Project

This project demonstrates a complete DevOps workflow for deploying an Online Shopping Application.

The application is containerized using Docker and deployed on Kubernetes through a Jenkins CI/CD pipeline.

---

## 🚀 Project Architecture

```text
Developer
    │
    ▼
GitHub Repository
    │
    ▼
GitHub Webhook
    │
    ▼
Jenkins Pipeline
    │
    ├── Build Application
    ├── Build Docker Image
    └── Deploy to Kubernetes
            │
            ▼
      Kubernetes Cluster
            │
            ├── Deployment
            ├── ReplicaSet
            └── Pods
            │
            ▼
    Online Shopping Application
🛠️ Technologies Used
Git
GitHub
Docker
Jenkins
GitHub Webhooks
Kubernetes
Nginx
Linux
📁 Project Structure
online_shopping_app/
│
├── Dockerfile
├── Jenkinsfile
│
├── kubernetes/
│   ├── deployment.yaml
│   └── service.yaml
│
└── Application Files
🔄 CI/CD Pipeline Workflow

The project uses Jenkins to automate the deployment process.

Pipeline Process
The developer pushes code to the GitHub repository.
GitHub sends a webhook request to Jenkins.
Jenkins triggers the pipeline automatically.
Jenkins pulls the latest source code.
A Docker image is built from the application.
The application is deployed to Kubernetes.
Kubernetes creates and manages the application pods.
The application becomes available through the Kubernetes service.
🐳 Docker

The application is containerized using Docker.

Build Docker Image
docker build -t online-shopping-app .
Run Docker Container
docker run -d -p 8080:80 online-shopping-app
☸️ Kubernetes Deployment

Apply the Kubernetes deployment:

kubectl apply -f kubernetes/deployment.yaml

Create the Kubernetes service:

kubectl apply -f kubernetes/service.yaml

Check the deployment:

kubectl get deployment -n online-shopping

Check running pods:

kubectl get pods -n online-shopping

Check services:

kubectl get svc -n online-shopping
📊 Deployment Status

The application is successfully deployed on Kubernetes.

Example:

Deployment: online-shop
Replicas: 2
Available Pods: 2
Status: Running
🔗 Complete DevOps Workflow
GitHub
   ↓
GitHub Webhook
   ↓
Jenkins
   ↓
Docker Build
   ↓
Kubernetes Deployment
   ↓
Pods Running
   ↓
Online Shopping Application
🎯 Project Goals

The purpose of this project is to gain practical experience with:

CI/CD Pipeline Automation
Git and GitHub
Docker Containerization
Jenkins Automation
GitHub Webhooks
Kubernetes Deployments
Kubernetes Services
ReplicaSets and Pods
Container Orchestration
