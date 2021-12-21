### FSx for Windows File Server
- Fully managed **native windows** file servers/shares - not emulated
- Designed for **integration** with **windows evironments**
- Integrates with **Directory Service** or **Self-Managed AD**
- **Single** or **Multi-AZ** within a VPC
- **On-demand** and **Scheduled** Backups
- Accesible using **VPC, Peering, VPN, Direct Connect**
- Advanced shared file system accessible over **SMB** (Server Message Block)
- <span style="color:orange;font-weight:bold">Native windows file system, supports de-duplication (sub file), Distributed File System (DFS), KMS at-rest encryption and enforced encryption in-transit</span> 
- VSS - User-Driven Restores (Windows stuff)
- Windows permission model
- Managed - no file server admin

### FSx for Lustre
- Managed **Lustre** - Designed for **HPC**(High Perfromance Computing) 
    - **LINUX** clients (**POSIX**)
- Machine Learning, Big  Data, Financial Modeling
- **100's GB/s** throughput & **sub millisecond** latency
- Deployment types - Persistent or Scratch
- Scratch - Highly optmised for **Short term** with no replication but fast - **pure performance**
- Persistent - **longer term, HA (in one AZ)**, **self-healing** with **replication**
- Accessible over **VPN** or **Direct Connect**
- S3 can be set as repository for file system and data is `lazy loaded` and `hsm_archive` can be used to export data back to S3. <span style="color:red;font-weight:bold">NO AUTOMATIC SYNCHRONIZATION</span>
- **Backup to S3** with both deployment types (Manual of Automatic 0-35 day retention)

**Data Storage**

- Metadata stored on Metadata Targets (**MDTs**)
- Objects are stored on called object storage targets (**OSTs**) (**1.17TiB**)
- **Baseline** Performance based on size
- Size - min **1.2TiB** then increments of **2.4TiB**
- For **Scratch** - Base **200 MB/s** per **TiB** of storage
- Persistent offers **50MB/s, 100Mb/s** and **200MB/s** per **TiB** of storage
- Burst upto **1300 Mb/s** per **TiB** (Credit systems)


### Elastic File System (EFS)
> NFS - Network File System

- **EFS** is an implementation of **NFSv4** - Linux Only
- EFS **Filesystems** can be <span style="color:red;font-weight:bold">mounted in Linux</span>
- **Shared** between many EC2 instances
- Private service, integrated via **mount targets** inside a VPC
    - mutliple **mount targets** in multiple AZ for **HA**
- Access via  - **VPN or DX**
- **General Purpose** and **Max I/O** Performance Modes
- **Bursting** and **Provisioned** Throughput Modes
- **Standard** and **Infrequent Access** (IA) Classes
    - Lifecycle Policies can be used to move between the classes
