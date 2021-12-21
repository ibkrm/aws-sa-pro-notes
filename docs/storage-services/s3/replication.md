### S3 Replication
**CRR** - Cross Region Replication

**SRR** - Same Region Replication

- **Replication configuration** applies to **source bucket**
- IAM role is assigned for replcation - with trust to **s3.amazonaws.com**
    - permission policy to move objects in both buckets

- For replication between different accounts 
    - destination bucket should have proper bucket policy to allow IAM role in source bucket acccount to write and replicate objects

- Replicaiton could be applied to all objects or a subset of objects (filter with **prefix and/or tags**)
- Storage class in destination bucket - default to same as source bucket (could be configured)
- Ownership of the destination objects - deafult is the soruce account (could be changed to different destination account)
- **Replication Time Control** (RTC) - 15 mins ETA
- Only applies to the objects after the **replication is enabled** and **VERSIONING** needs to be enabled in both buckets
- **One-way replication** - from source to destination

- Handles **unencrypted** objects as well as objects **encrypted with SSE-S3 & SSE-KMS**(with extra config)
- Source bucket owner needs permissions to objects
- Does not replicate -<span style="color:red;font-weight:bold">systems events, Glacier or Glacier Deep Archive</span>
- <span style="color:red;font-weight:bold">Does not replicate DELETE</span>

**Why use replication .. ?**

|SRR| CRR|
|:---:|:---:|
|Log aggregation| Global Resiliency Improvements|
|Prod and Test Sync| Latency Reduction|
|Resilience with strict sovereignty - regional| |