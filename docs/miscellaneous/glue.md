### Overview
- <span style="color:orange;font-weight:bold">Serverless ETL (Extract, Transform & Load) </span> service
    - different than **datapipeline** (which can do ETL) and uses servers (**EMR**)
- **Moves** and **Transforms** data between **source** and **destination**
    - use glue job to enrich data in serverless way
- **Crawls** data sources and generates the **AWS Glue Data Catalog**
- Data **Source:Store** - S3, RDS, JDBC compatible & DynamoDB
- Data **Source:Streams** - Kinesis Data Stream & Apache Kafka
- Data **Targets** - S3, RDS, JDBC Databases


### AWS Glue - Data Catalog
- **Persistent metadata** about data sources within a region
- **One catalog** per **region** per **account**
    - <span style="color:red;font-weight:bold">Avoids data silos.. </span>
- <span style="color:orange;font-weight:bold">Amazon Athena, Redshift Spectrum, EMR & AWS Lake Formation all use Data Catalog</span>
    - configure crawlers for data sources
- **Either AWS Glue or datapipeline**

</br>

![aws-glue](aws-glue.png)