## NOTE 

- PV = Persistent Volume : 
    is the place where you store or backup you rdata (could be NFS , Cloud Storages , ... )

- PVC = Persistent Volume Claim: 
    it is a claim to allocate or claim a specific PV to use for storage 

PVC must be bound to PV 

Demo 2 ways 
1. Static Provisioning ( Manual approach )
- Create PV, create PVC all by yourself 
2. Dynamic Provisioning ( Using external NFS provisioner )
- Only need to create the PVC , PV will be automatically created 
- Provider better handling , ...
```bash
helm repo add nfs-subdir-external-provisioner https://kubernetes-sigs.github.io/nfs-subdir-external-provisioner/
helm repo update # same as sudo apt  update 

helm install nfs-subdir-external-provisioner nfs-subdir-external-provisioner/nfs-subdir-external-provisioner \
    --set nfs.server=10.148.0.2 \
    --set nfs.path=/srv/nfs_shared/spring-demo-pv
```