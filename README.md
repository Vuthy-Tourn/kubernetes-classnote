# Kubernetes Learning Repository 🚀
<p align="center">
  <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/3/39/Kubernetes_logo_without_workmark.svg/960px-Kubernetes_logo_without_workmark.svg.png" width="200" alt="Kubernetes Logo">
</p>

This repository is a **complete learning guide for Kubernetes**, from fundamentals to practical deployment strategies.  

---

## 📌 What You Will Learn

- Kubernetes core concepts and architecture
- Working with Pods, Deployments, and Services
- Configuration and secrets management
- Storage and networking
- Deployment strategies
- Basic troubleshooting and best practices

---

## 🧠 Kubernetes Overview

**Kubernetes (K8s)** is an open-source container orchestration platform that helps you:
- Deploy applications
- Scale containers automatically
- Heal failed workloads
- Manage containerized systems efficiently

---

## 🏗 Kubernetes Architecture

### Control Plane
- **API Server** – Main entry point for cluster communication
- **etcd** – Stores cluster state
- **Scheduler** – Assigns Pods to nodes
- **Controller Manager** – Maintains desired state

### Worker Nodes
- **kubelet** – Manages Pods on the node
- **kube-proxy** – Handles networking
- **Container Runtime** – Docker / containerd

---

## 📦 Core Kubernetes Objects

### Pod
- Smallest deployable unit
- One or more containers
- Shared network and storage

### ReplicaSet
- Ensures a specified number of Pods are running

### Deployment
- Manages ReplicaSets
- Supports rolling updates and rollbacks

### Service
- Exposes applications inside or outside the cluster
- Types:
  - ClusterIP
  - NodePort
  - LoadBalancer

---

## ⚙ Configuration Management

### ConfigMap
- Store non-sensitive configuration data

### Secret
- Store sensitive data (passwords, tokens)

---

## 💾 Storage in Kubernetes

### Volumes
- Temporary storage tied to Pod lifecycle

### PersistentVolume (PV)
- Cluster-wide storage resource

### PersistentVolumeClaim (PVC)
- Request storage for Pods

---

## 🌐 Networking Concepts

- Each Pod has its own IP
- Services provide stable access to Pods
- Ingress manages external HTTP/HTTPS traffic

---

## 🚀 Deployment Strategies

### Rolling Update
- Default Kubernetes strategy
- Gradually replaces Pods

### Blue–Green Deployment
- Two environments: Blue (live), Green (new)
- Instant rollback
- Zero downtime

### Canary Deployment
- Release to a small group of users first
- Gradually increase traffic

---

## 🛠 Useful kubectl Commands

```bash
kubectl get pods
kubectl describe pod <pod-name>
kubectl logs <pod-name>
kubectl apply -f file.yaml
kubectl delete -f file.yaml
