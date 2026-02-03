kubectl get svc -n kube-system

# make sure to change from NodePort to ClusterIP 
kubectl edit svc kubernetes-dashboard -n kube-system

# getting service of kubernetes-dashboard
kubectl get svc -A | grep "kubernetes-dashboard"

# getting namespace 
kubectl get ns -A 

# Copy token and login in Kubernetes Dashboard
kubectl -n kubernetes-dashboard create token admin-user --duration=24h 

