## Note for service

**Service** provide a way to expose your application running in a Kubernetes cluster to other applications or users outside the cluster.

- ClusterIP:  ( stable IP and domain name ) working within cluster.
- NodePort: for dev/testing, it can be a concern of security because we need to allow port "30000-32767"
- Loadbalancer
- Externalname:

## Note for ingress

 **Ingress** is a way to expose HTTP and HTTPS services to the outside world using a single IP address. 

- Host-based: one domain name per service
- Path-based: one domain point to service by determine the path 