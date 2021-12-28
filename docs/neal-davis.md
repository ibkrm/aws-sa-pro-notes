#### Migraiton tools
https://docs.aws.amazon.com/prescriptive-guidance/latest/migration-tools/aws-services.html

#### AWS Migration Hub 
AWS Migration Hub provides a single place to store IT asset inventory data while tracking migrations to any AWS Region. After migration, use Migration Hub to accelerate the transformation of your applications to native AWS

- Centralized tracking
- Migration flexibility
- Discovery, assessment, and planning
- Fast-track application refactor

#### AWS cloud Adoption Readiness Tool (CART)
https://cloudreadiness.amazonaws.com/#/cart

Completing our cloud readiness assessment with CART can transform your idea of moving to the cloud into a detailed plan that follows AWS Professional Services best practices.

#### AWS Application Discovery Service
Collects server specification information, performance data, and details of running processes and network connections

#### AWS Organization
- The deny list SCP at the root level will not allow the restricted actions to be allowed at any level beneath so this will not work.
- Move SCP from root to OU to update OUs for actions like DMS

### AWS Systems Manager Agent for secured and restricted access

### NLBs do not have security groups configured
and pass connections straight to EC2 instances with the source IP of the client preserved (when registered by instance-id).

### Improve the transfer speed from your data source to the Snowball
in the following ways, ordered from largest to smallest positive impact on performance:

1. Use the latest Mac or Linux Snowball client

2. Batch small files together

3. Perform multiple copy operations at one time

4. Copy from multiple workstations

5. Transfer directories, not files

### [AWS::S3::Bucket PublicAccessBlockConfiguration](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-properties-s3-bucket-publicaccessblockconfiguration.html)
to apply only required public block configurations


### Update the AWS CloudFormation template to include the 
[AWS::Budgets::Budget::resource](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-budgets-budget.html) with the NotificationsWithSubscribers property" is a correct answer.

### Step Functions input includes
SQS queue

### S3 multi-part upload
to speed up the uploads

### Lambda Alias can be used 
to route based on weights between 2 versions of lambda

### ElasticBeanStalk can perform blue/green 
swap environment urls

### Cloudwatch events for 
- instance launch and termination

### Lambdas alias and weighted traffic between versions

### Cannot create unectypted snapshot of encrypted DB instances and
cannot create unencrypted replicas of encrypted DB instances

### API Gateway can be regional as well edge-optimized
caching also can be enabled to minimize load on backends/database

### Cannot create snapshot of instance in one region to another directly
instead need to copy the snapshot of instance in that region to another

### AWS recommends to create IAM roles and resources in the account where 
the respecitve task has to be executed but also **recommend that you enable AWS CloudTrail and keep relevant CloudTrail trails and logs in the management account.**

### Organizations service control policies (SCPs) do not work 
to restrict any users or roles in the management account.

### AppSync - GraphQL API can fetch from multiple data soruces and 
congnito groups can be used with resolvers to provide authorization based on identity

### API Gateway with WAF web ACL to allow for IPs
- create a usgae plan for reuqest limit and associate with the API
- create an API key and add it to the usage plan