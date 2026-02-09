## Node & Pod Affinity

### Node Affinity

*   Controls **which nodes** a Pod can run on
    
*   Based on **node labels**
    
*   Used for **hardware, isolation, environment separation**
    
*   Types:
    
    *   **Required** → must match or Pod won’t run
        
    *   **Preferred** → best effort
        
*   Example use cases:
    
    *   GPU workloads
        
    *   SSD-only apps
        
    *   Prod vs Dev nodes
        

👉 Think: **“Which machine?”**

### Pod Affinity

*   Controls **which Pods should be placed together**
    
*   Based on **pod labels**
    
*   Uses **topology** (node, zone, region)
    
*   Improves **performance & locality**
    
*   Example use cases:
    
    *   App + cache on same node
        
    *   Frontend near backend
        

👉 Think: **“Place near these Pods”**

## Key operators
| Operator     | Meaning                  |
| ------------ | ------------------------ |
| In           | value must match         |
| NotIn        | value must NOT match     |
| Exists       | label key exists         |
| DoesNotExist | label key does not exist |
