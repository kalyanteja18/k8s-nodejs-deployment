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
|       ngrok Tunnel     |
|          │             |
|  🌍 Public Internet     |
+-------------------------+

