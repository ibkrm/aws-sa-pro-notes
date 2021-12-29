#### When to use AWS Shield Advance
AWS Shiled Advance - SYN floods and UDP reflection attacks

#### Initial version of s3 object is null 
if the version is enabled after the object is uploaded

#### Set reserved concurrency limit
to ensure the lambda function does not throttle concurrency for the account

- **Reserved concurrency** – Reserved concurrency creates a pool of requests that can only be used by its function, and also prevents its function from using unreserved concurrency.

- **Provisioned concurrency** – Provisioned concurrency initializes a requested number of execution environments so that they are prepared to respond to your function’s invocations.

#### Explicit deny policy based on tagged resources

#### Instance profile does not suppor role ARN rather insance profile ARN

#### AWS PrivateLink
- Allow inbound rules in EC2 SG from NLB subnet range
- NACL associated with NLB subnet allow access (IPs) -> to and form EC2 subnets


#### Storage volumes 
- cached volume capacity - 1024TB in size
- stored volume capacity  - 512 TB in size

#### Global Accelator cannot host static content
- Also SQS queue for work distribution and ephemeral storage
- Also ASG for EC2 instances

#### AWS Systems Manager Patch Manager
Amazon RDS does not support certain features in Oracle such as Multitenant Database, Real Application Clusters (RAC), Unified Auditing, Database Vault, and many more.

#### AWS clodufront presigned URL or s3 presigned url private access to object for S3 buckets
- **cloudfront cookies** to allow access to group of objects


#### AWS OpsWorks ==> one stack - two layers (web and chat) -- 1 recipe

#### Set up a forward proxy server in your VPC to manage outbound access using URL based rules
[How to set up an outbound VPC proxy with domain whitelisting and content filtering](https://aws.amazon.com/blogs/security/how-to-set-up-an-outbound-vpc-proxy-with-domain-whitelisting-and-content-filtering/)

#### Configure a Challenge-Handshake Authentication Protocol (CHAP) to authenticate iSCSI and initiator connections.
- provides protection against playback attacks by requiring authentication to access storage volume targets


#### ProvisionedThroughputExceededException in DynamoDB means
you exceeded your maximum allowed provisioned throughout

#### Kinesis stream group batches
- read stream in batch size for lower no. of invocations of lambda

#### Delegate access across AWS accounts using IAM roles
https://docs.aws.amazon.com/IAM/latest/UserGuide/tutorial_cross-account-with-roles.html

#### no iscii with EC2 - already comes with EBS storge
- only on-premise

### Custom SAML based Identity solution that integrates with company ldP
- Ensure that the ARN of the SAML provider, the ARN of the created IAM role, and SAML assertion from the IdP are all included when the federated identity web portal calls the AWS STS AssumeRoleWithSAML API.
- Ensure that the appropriate IAM roles are mapped to company users and groups in the IdP’s SAML assertions.

- Check the company’s IdP to ensure that the users are all part of the default AWSFederatedUser IAM group which is readily available in AWS.


#### Kafka - fetch messages from  and produce to kinesis stream
- lambda to process kinesis stream and `websocket` for web applications needing constant stream such as stock
  
#### Best practice to keep the audit data within the account
