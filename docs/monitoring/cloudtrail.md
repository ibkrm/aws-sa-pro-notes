CloudTrail is a product which logs API calls and account events.

### CloudTrail Essentails
- Log API calls/activities as a **CloudTrail Event**
- **90 days** stored by default in **Event History**
    - **enabled by default** - no cost from AWS 
- Custmize by creatign 1 or more trails
    - **Management events** - management operations (control plane) - ec2 launch, terminate
    - **Data Events** - resouces event (object upload in s3) & lambda - <span style="color:orange;font-weight:bold">extra cost - not by default</span>
- By **default**, only management events are looged
- It can be configured to store data in S3 or Cloudwatch logs
- **Global services** logged their events in `us-east-1`
- Trail can be `one region` or `all regions`
- <span style="color:red;font-weight:bold">NOT REALTIME</span> - there is a delay
