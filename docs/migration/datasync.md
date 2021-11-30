### AWS DataSync
- Data Transfer service **TO** and **FROM** AWS
- **Use cases**
    - Data Migration
    - Achiving cold data
    - Data Protection
    - Data movement for timely in-cloud processing 
    - **DR/BC** - Disaster Recovery/Business continuity
- ..designed to work at huge scale (**agent**)
- Retains **metadata** (e.g. **permissions/timestamps**)
- Built in **data validation**

#### Key Features
- **Scalable** - 10GBps per agent (~100TB per day)
- **Bandwidth Limiters** (avoid link saturations)
- **Incremental** and **scheduled** transfer options
- **Compression** and **encyrption** 
- **Automatic recovery** from transit errors
- AWS **Service Integration** - S3, EFS, FSx
    - Support transfering data between one AWS service to another
- Pay as you use.. per **GB** cost for data moved

#### Components
- **Task** - A `job` within DataSync, defines what is being synced, how quickly, FROM where TO where
- **Agent** - Software to **READ** and **WRITE** to on-premise data stores using **NFS** or **SMB**
- **Location** - every task has two locations FROM and TO. 
    e.g. - NFS, SMB (Server Message Block), EFS, FSx and S3 