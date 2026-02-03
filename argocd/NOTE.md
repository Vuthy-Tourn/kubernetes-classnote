# getting service of argocd-server
kubectl get svc -A | grep "argocd-server"

# It must be filled with the secret that provided by ArgoCD
kubectl get secret -A | grep "argocd"

# username of argo is: admin 
# get your initial password 
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d