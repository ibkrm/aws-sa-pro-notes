### Cloudwatch Metrics
- **Ingestion, Storage and Management of Metrics**
- Public service
    - AWS service integration
    - Agent for internal metrics 
    - On-premise and application integration via API/Agent
- **Cloudwatch** **ALARM** can be created off **metrics** and alram notification can be sent to multiple AWS resources like **SNS, Autoscaling policy and EventBridge**
    - threshold - **OK or ALARM**

**DATA**

- **Namespace** = metrics name (`CPUUtilization`) => **dimensions** (`name=InstanceId, value=i-instanceid`)
    - Aggregate data using `dimensions`
- **Datapoint** = timestamp with value (optional) 
- **Resolution** = Standard(60s granularity) - **1s granularity for additional charge**
- **Statistic** - Min, Max, Sum, Average
- **Percentile** - e.g. **p95** & **p97.5**

### Cloudwatch Logs
**CloudWatch logs** is a product which can store, manage and provide access to logging data for on-premises and AWS environments including systems and applications

- **Public Service** - store, monitor and access log data
-  **AWS, On-Premises, IOT** or any application
-  **CWAgent** - system or custom application logging
- **VPC Flow Logs**
- **Cloudtrail**.. Account events and AWS API Calls
- **Elastic Beanstalk, ECS container logs, API GW and Lambda execution logs**
- **Route53** - Log DNS Requests
- **Global service** logs to `us-east-1` 
- 
- **Log Groups** 
    - by default retain indefinitely
    - encryption
    - permissions via policy
    - metric filter in log events ==> generates metric
    - metric can be used to create and trigger alarm
- **S3 Export** - Create-Export-Taks (not real time)
- **Log Stream** - subgroupping of log group for instances or lambda execution 
- **LogEvent** - `Timestamp` `Raw Message`

**Subscriptions**
- Realtime per log group
- **Subscription Filter** -> destination ARN 
    - **Kinesis Data Firehose** - near realtime to S3 
    - **Elastic Search** - real time
    - **Lambda Function** - relatime
    - **Kinesis Data Stream** - realtime

- **Clouwatch logs Aggregation**
    - **Multiple log groups** with subscription filters ==> **Kinesis data Stream** ==> **Kinesis Data Firehose** ==> **S3**
  