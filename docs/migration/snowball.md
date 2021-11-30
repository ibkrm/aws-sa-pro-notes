### AWS Snowball
- Move large amounts of data **IN** and **OUT** of AWS
    - expensive to transfer via netowrk
    - too much data to be transmitted via network

- Physical storage => **suitcase** or **truck**

#### Snowball
- Ordered from AWS - log a job - device delevered (not instant)
- Data Encryption uses KMS - at rest
- **50TB** or **80TB**
- **1 GBps** (RJ45 1GBas-TX) or **10 GBps** (LR/SR) Network
- 10 TB <--> 10PB **economical range**  (**multiple devices**)
- Multiple devices to **multiple locations**
- **ONLY STORAGE DEVICE**

#### Snowball Edge
- Both **compute** and **storage**
- **Larger Capacity** vs snowball
- **10** GBps, **10/25** (SFP), **45/50/100** (QSFP+)
- **Storage Optimized** - 80TB, 24 vCPU, 32 GiB RAM
    - **withEC2** - **1TB SSD**
- **Compute Optimized** - 100TB + NVME, 52vCPU and 208 GiB RAM
    - **Compute Optimized** - As above ... **with a GPU**
- Ideal for remote sites or where data processing on ingestion is needed

#### Snowmobile
- Portable DC wihtin a shipping container on a **truck** 
- Special Order
- Ideal for single location when **10PB+** is required
- Up to **100PB** per snowmobile
- Not economical for **multi-site** (unless huge) or sub **10PB**
