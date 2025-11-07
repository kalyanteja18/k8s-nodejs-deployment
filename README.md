# Kubernetes Deployment of a Simple Node.js Web App
# 🚀 Kubernetes Deployment of a Node.js Web App

This project demonstrates a **complete DevOps workflow**: containerizing a Node.js application with Docker, deploying it on a local **Kubernetes cluster (Kind)**, and exposing it publicly using **ngrok**.

---

## 🧠 Overview
I deployed an open-source Node.js sample app inside a Kubernetes cluster created using [Kind](https://kind.sigs.k8s.io/).  
The app is accessible publicly through ngrok, showcasing end-to-end container orchestration skills.

---

## 🧩 Architecture Diagram
```text
+-----------------------+
|  Local Machine (WSL2) |
|  ┌──────────────────┐ |
|  |  Docker Engine   | |
|  └──────────────────┘ |
|          │             |
|   kind (K8s Cluster)   |
|   ┌──────────────────┐ |
|   │  Node.js Pods    │ |
|   │  Service (NodePort)│
|   └──────────────────┘ |
|          │             |



Steps to Deploy

Create Kind cluster

kind create cluster --name devops-assignment


Build Docker image

docker build -t nodejs-sample .


Apply Kubernetes manifests

kubectl apply -f k8s-deployment.yaml
kubectl apply -f k8s-service.yaml


Expose locally

kubectl port-forward svc/nodejs-svc 8080:80


Make public using ngrok

ngrok http 8080


Access your app

https://mikel-billety-martin.ngrok-free.dev
|       ngrok Tunnel     |
|          │             |
|  🌍 Public Internet     |
+-------------------------+

