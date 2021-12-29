### Database Migration Service (DMS)
AWS Database Migration Service (AWS DMS) is a cloud service that makes it easy to migrate **relational databases, data warehouses, NoSQL databases**, and other types of data stores. You can use AWS DMS to migrate your data into the AWS Cloud or between combinations of cloud and on-premises setups.

- Managed Database Migration Service
- Runs using a replication instance
- **Source** and **Destination Endpoints** point at ..
    - **Source** and **Target** Databases
- <span style="color:red;font-weight:bold">One Endpoint must be on AWS</span>
- Migraiton Types:
    - **Full Load** - one off migration of all data
    - **Full Load + CDC (change data capture)** - also captures ongoing changes in the source DB
    - **CDC Only** - copy existing data using other native tooling and only apply data changes 
- Does not support schema conversion but ...
    - tool available called **Schema Conversion Tool(SCT)**
    - assist with Schema Conversion

#### Schema Conversion Tool (SCT)
- SCT is used when converting **one database** engine to **another**
    - .. including **DB** -> **s3**
    - on-premises MSSQL -> RDS MySQL
    - on-premises ORACLE -> Aurora
- SCT <span style="color:red;font-weight:bold">is not used when migrating between DB's of the same type</span>
    - .. On-premise **MySQL -> RDS MySQL**
- Works with database types like
    - **OLTP DB Types** - MySQL, Oracle, MSSQL
    - **OLAP** - Teradata, Oracle, Vertica, Greenplum


#### DMS & Snowball
- Larger migrations might be multi-TB in size 
    - moving data over takes time and consumes capacity
- DMS can utilise snowball..
- **Steps**:
    - **1.** Use SCT to extract data locally and move to a snowball device (generic fie format)
    - **2.** Ship the device back to AWS.They load onto an S3 bucket.
    - **3.** DMS migrates from S3 into the target store
    - **4.** CDC can capture data changes -> s3 (intermediary) -> write to target DB      