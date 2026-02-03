# ArgoCD Access Guide

This guide explains how to access the **ArgoCD** in your cluster.

---

## ArgoCD

### 1. Check ArgoCD Service

```
kubectl get svc -A | grep "argocd-server"
```

### 2. Verify ArgoCD Secrets

```
kubectl get secret -A | grep "argocd"
```

### 3. Default Credentials

* **Username:** `admin`
* **Password:** (Initial password generated from secret)

```
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d
```

> Use this username and password to login to the ArgoCD web interface.
