### Overview
- **Cluster Mode**
- A single **primary** instance + **0** or more **replicas**
    - primary instance - reads and writes
    - secondary instance - only reads
    - <span style="color:orange;font-weight:bold">upto 15 replicas - can be anyone to be primary during failover</span>
- <span style="color:orange;font-weight:bold">No local storage</span> - uses **cluster volume** (SSD based)
    - faster provisioning & improved availability & performance
    - **All SSD Based** - `high IOPs, low latency` 
    - Pay for only what is being used
    - Volumes are replicated **synchronously**
    - **High water mark** - billed for most used
    - No performance degradation during replication
    - Replicas can be **added and removed** without requiring storage provisioning

- **Endpoints**
    - **Cluster Endpoint** - points to primary instance
    - **Reader Endpoint** - pooints to replicas (load-balance between multiple replicas)
    - **Custom Endpoint** - custom endpoint using db identifiers


### Cost
- <span style="color:red;font-weight:bold">No Free Tier Option</span>
- Does not support micro instances
- Beyond **RDS singleAZ (micro)** Aurora offers better value
- **Compute** - hourly charge, per second, 10 minutes minimum
- **Storage** - GB-Month consumed, IO cost per request
- **100% DB Size** in backups are included

### Restore, Clone and Backtrack
- Backups in Aurora work in the same ways as RDS
- Restores creates a <span style="color:red;font-weight:bold">new cluster</span>
- Backtrack can be used which allow <span style="color:red;font-weight:bold">in-place rewinds</span> to a previous point in time
- Fast clone make a new database MUCH faster than copying all the data - <span style="color:red;font-weight:bold">copy-on-write</span>
    - just refrence the origin storage
    - store the difference

### Aurora Serverless
- Scalable => **ACU** - Aurora Capacity Units
    - <span style="color:red;font-weight:bold">MIN & MAX ACU</span> is set for cluster
    - Scalable between MIN and MAX based on the load
- Consumption **billing per-second** basis
- Same reslience as Aurora (6 copies accross AZs)

#### Use Cases
- **Infrequently** used applications
- **New** applications
- **Variable** workloads
- **Unpredictable** workloads
- **Development** and **test** databases
- **Multi-tenant** applications

### Aurora Multi-Master
- Default Aurora mode is **Single-Master**
- Failover takes time - replica promoted to `R/W`
- In Multi-Master mode **all instances are R/W**
    - quoram of nodes to agree on the data to be written
- Traffic is instantly switched to different master instance if one master fails