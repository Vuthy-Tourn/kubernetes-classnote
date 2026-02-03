# Kubernetes Dashboard & ArgoCD Access Guide

This guide explains how to access the **Kubernetes Dashboard** in your cluster.

---

## Kubernetes Dashboard

### 1. Check Services in the `kube-system` namespace

```
kubectl get svc -n kube-system
```

### 2. Change Dashboard Service Type (if needed)

> Make sure to change from `NodePort` to `ClusterIP`:

```
kubectl edit svc kubernetes-dashboard -n kube-system
```

### 3. Verify Kubernetes Dashboard Service

```
kubectl get svc -A | grep "kubernetes-dashboard"
```

### 4. Verify Namespace

```
kubectl get ns -A
```

### 5. Generate Access Token

```
kubectl -n kubernetes-dashboard create token admin-user --duration=24h
```

> Copy the generated token and use it to login to the Kubernetes Dashboard.