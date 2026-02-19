## NOTE 

- PV = Persistent Volume : 
    is the place where you store or backup you rdata (could be NFS , Cloud Storages , ... )

- PVC = Persistent Volume Claim: 
    it is a claim to allocate or claim a specific PV to use for storage 

PVC must be bound to PV 

Demo 2 ways 
1. Manual approach 
- Create PV, create PVC all by yourself 
2. Using external NFS provisioner 
- Only need to create the PVC , PV will be automatically created 
- Provider better handling , ...