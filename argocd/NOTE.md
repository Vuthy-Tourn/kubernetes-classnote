# ArgoCD Access Guide

This guide explains how to access the **ArgoCD** in your cluster.

---

## ArgoCD

### 1. Check ArgoCD Service

```bash
kubectl get svc -A | grep "argocd-server"
```

### 2. Verify ArgoCD Secrets

```bash
kubectl get secret -A | grep "argocd"
```

### 3. Default Credentials

* **Username:** `admin`
* **Password:** (Initial password generated from secret)

```bash
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d
```

> Use this username and password to login to the ArgoCD web interface.

## Configure the github secret for secured communication ( Github Webhook )

```bash
kubectl get secret -n argocd 
kubectl edit secret argocd-secret -n argocd 

echo -n "securedpass123" | base64
webhook.github.secret: <your-base64-token> 
```

## How to use it ( inside Github repo)

1. Go to `GitHub repo → Settings → Webhooks → Add webhook`

2. Payload URL: `https://<ARGOCD_SERVER>/api/webhook` (your Argo CD URL)

3. Content type: application/json

4. Secret: `securedpass123` (the decoded value)

5. Events: usually Just the push event