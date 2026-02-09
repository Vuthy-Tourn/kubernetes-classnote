## Anti-Affinity (Node & Pod)

### Node Anti-Affinity

-   Prevents Pods from running on **certain nodes**
    
-   Based on **node labels**
    
-   Used to **avoid specific machines**
    
-   Common use cases:
    
    -   Avoid unstable or maintenance nodes
        
    -   Avoid shared / low-resource nodes
        
    -   Isolate workloads
        

👉 Think: **“Do NOT run on these nodes”**

* * *

### Pod Anti-Affinity

-   Prevents Pods from running **near certain Pods**

-   Based on **pod labels**
    
-   Uses **topology keys** (node, zone, region)
    
-   Used to **spread Pods** for high availability
    

👉 Think: **“Do NOT run near these Pods”**