AWS Certified Solutions Architect – Professional
(SAP-C01) Exam Guide
Version 2.0 SAP-C01 1

## Introduction
The AWS Certified Solutions Architect – Professional (SAP-C01) exam is intended for individuals who
perform a solutions architect role. The exam validates a candidate’s advanced technical skills and
experience in designing distributed applications and systems on the AWS platform.

The exam also validates a candidate’s ability to complete the following tasks:

  - Design and deploy dynamically scalable, highly available, fault-tolerant, and reliable applications
    on AWS
  - Select appropriate AWS services to design and deploy an application based on given requirements
  - Migrate complex, multi-tier applications on AWS
  - Design and deploy enterprise-wide scalable operations on AWS
  - Implement cost-control strategies

## Target candidate description
The target candidate should have 2 or more years of experience designing and deploying cloud
architecture on AWS. The target candidate has the ability to evaluate cloud application requirements and
make architectural recommendations for implementation, deployment, and provisioning applications on
AWS. The target candidate is capable of providing best practice guidance on architectural design spanning
multiple applications and projects, or an enterprise.

#### **Recommended AWS knowledge**
The target candidate should have the following knowledge:

  - Explain and apply the five pillars of the AWS Well-Architected Framework
  - Map business objectives to application/architecture requirements
  - Design a hybrid architecture using key AWS technologies
  - Architect a continuous integration/continuous delivery (CI/CD) process

#### <span style="color:orange;font-weight:bold">What is considered out of scope for the target candidate?</span>
The following is a non-exhaustive list of related job tasks that the target candidate is not expected to be
able to perform. These items are considered out of scope for the exam:

  - Machine learning
  - Amazon GameLift
  - Front-end development for mobile apps
  - 12-factor app methodology
  - In-depth knowledge of operating systems
  - Enterprise applications
  - Database schemas for high-scale persistent stores

To view a detailed list of specific tools and technologies that might be covered on the exam, as well as lists
of in-scope and out-of-scope AWS services, refer to the Appendix.

## Exam content
### Response types

There are two types of questions on the exam:

  - **Multiple choice**: Has one correct response and three incorrect responses (distractors)
  - **Multiple response**: Has two or more correct responses out of five or more response options
  
Select one or more responses that best completes the statement or answers the question. Distractors, orincorrect answers, are response options that a candidate with incomplete knowledge or skill might choose.

Distractors are generally plausible responses that match the content area.

Unanswered questions are scored as incorrect; there is no penalty for guessing. The exam includes 65 questions that will affect your score.

### Unscored content

The exam includes 10 unscored questions that do not affect your score. AWS collects information about candidate performance on these unscored questions to evaluate these questions for future use as scored questions. These unscored questions are not identified on the exam.

### Exam results
The AWS Certified Solutions Architect – Professional (SAP-C01) exam is a pass or fail exam. The exam is
scored against a minimum standard established by AWS professionals who follow certification industry
best practices and guidelines.
Your results for the exam are reported as a scaled score of 100–1,000. The minimum passing score is 750.
Your score shows how you performed on the exam as a whole and whether or not you passed. Scaled
scoring models help equate scores across multiple exam forms that might have slightly different difficulty
levels.

Your score report may contain a table of classifications of your performance at each section level. This
information is intended to provide general feedback about your exam performance. The exam uses a
compensatory scoring model, which means that you do not need to achieve a passing score in each
section. You need to pass only the overall exam.

Each section of the exam has a specific weighting, so some sections have more questions than others. The
table contains general information that highlights your strengths and weaknesses. Use caution when
interpreting section-level feedback.

#### Content outline
This exam guide includes weightings, test domains, and objectives for the exam. It is not a comprehensive listing of the content on the exam. However, additional context for each of the objectives is available to help guide your preparation for the exam. 

The following table lists the main content domains and their weightings. The table precedes the complete exam content outline, which includes the additional context.

The percentage in each domain represents only scored content.

|Domain |% of Exam|
|:---|:---:|
|Domain 1: Design for Organizational Complexity |12.5%|
|Domain 2: Design for New Solutions| 31%|
|Domain 3: Migration Planning |15%|
|Domain 4: Cost Control |12.5%|
|Domain 5: Continuous Improvement| 29%|
|**TOTAL** |100%||


### Domain 1: Design for Organizational Complexity
1.1. Determine cross-account authentication and access strategy for complex organizations.

  - Analyze the organizational structure
  - Evaluate the current authentication infrastructure
  - Analyze the AWS resources at an account level
  - Determine an auditing strategy for authentication and access

1.2 Determine how to design networks for complex organizations.

  - Outline an IP addressing strategy for VPCs
  - Determine DNS strategy
  - Classify network traffic and security
  - Determine connectivity needs for hybrid environments
  - Determine a way to audit network traffic
   
1.3 Determine how to design a multi-account AWS environment for complex organizations.

  - Determine how to use AWS Organizations
  - Implement the most appropriate account structure for proper cost allocation, agility, and security
  - Recommend a central audit and event notification strategy
  - Decide on an access strategy

### Domain 2: Design for New Solutions
2.1 Determine security requirements and controls when designing and implementing a solution.

  - Implement infrastructure as code
  - Determine prevention controls for large-scale web applications
  - Determine roles and responsibilities of applications
  - Determine a secure method to manage credentials for the solutions/applications
  - Enable detection controls and security services for large-scale applications
  - Enforce host and network security boundaries
  - Enable encryption in transit and at rest

2.2 Determine a solution design and implementation strategy to meet reliability requirements.

  - Design a highly available application environment
  - Determine advanced techniques to detect for failure and service recoverability
  - Determine processes and components to monitor and recover from regional service disruptions with regional failover

2.3 Determine a solution design to ensure business continuity.

  - Architect an automated, cost-effective back-up solution that supports business continuity
  across multiple AWS Regions
  - Determine an architecture that provides application and infrastructure availability in the event of a service disruption

2.4 Determine a solution design to meet performance objectives.

  - Design internet-scale application architectures
  - Design an architecture for performance according to business objectives
  - Apply design patterns to meet business objectives with caches, buffering, and replicas

2.5 Determine a deployment strategy to meet business requirements when designing and implementing a solution.

  - Determine resource provisioning strategy to meet business objectives
  - Determine a migration process to change the version of a service
  - Determine services to meet deployment strategy
  - Determine patch management strategy

### Domain 3: Migration Planning
3.1 Select existing workloads and processes for potential migration to the cloud.

  - Complete an application migration assessment
  - Classify applications according to the six Rs (re-host, re-platform, re-purchase, refactor, retire,
  and retain)

3.2 Select migration tools and/or services for new and migrated solutions based on detailed AWS knowledge.

  - Select an appropriate database transfer mechanism
  - Select an appropriate data transfer service
  - Select an appropriate data transfer target
  - Select an appropriate server migration mechanism
  - Apply the appropriate security methods to the migration tools

3.3 Determine a new cloud architecture for an existing solution.

  - Evaluate business applications and determine the target cloud architecture
  - Break down the functionality of applications into services
  - Determine target database platforms

3.4 Determine a strategy for migrating existing on-premises workloads to the cloud.

  - Determine the desired prioritization strategy of the organization
  - Analyze data volume and rate of change to determine a data transfer strategy
  - Evaluate cutover strategies
  - Assess internal and external compliance requirements for a successful migration
 
### Domain 4: Cost Control
4.1 Select a cost-effective pricing model for a solution.

- Purchase resources based on usage requirements
- Identify when to use different storage tiers

4.2 Determine which controls to design and implement that will ensure cost optimization.

- Determine an AWS-generated cost allocation tags strategy that allows mapping cost to
business units
- Determine a mechanism to monitor when underutilized resources are present
- Determine a way to manage commonly deployed resources to achieve governance
- Define a way to plan costs that do not exceed the budget amount

4.3 Identify opportunities to reduce cost in an existing architecture.

- Distinguish opportunities to use AWS Managed Services
- Determine which services are most cost-effective in meeting business objectives

### Domain 5: Continuous Improvement for Existing Solutions

5.1 Troubleshoot solutions architectures.

- Assess an existing application architecture for deficiencies
- Analyze application and infrastructure logs
- Test possible solutions in non-production environment

5.2 Determine a strategy to improve an existing solution for operational excellence.

- Determine the most appropriate logging and monitoring strategy
- Recommend the appropriate AWS offering(s) to enable configuration management
automation

5.3 Determine a strategy to improve the reliability of an existing solution.

- Evaluate existing architecture to determine areas that are not sufficiently reliable
- Remediate single points of failure
- Enable data replication, self-healing, and elastic features and services
- Test the reliability of the new solution

5.4 Determine a strategy to improve the performance of an existing solution.

- Reconcile current performance metrics against performance targets
- Identify and examine performance bottlenecks
- Recommend and test potential remediation solutions

5.5 Determine a strategy to improve the security of an existing solution.

- Evaluate AWS Secrets Manager strategy
- Audit the environment for security vulnerabilities
- Enable manual and/or automated responses to the detection of vulnerabilities

5.6 Determine how to improve the deployment of an existing solution.

- Evaluate appropriate tooling to enable infrastructure as code
- Evaluate current deployment processes for improvement opportunities
- Test automated deployment and rollback strategies

### Appendix
#### Which key tools, technologies, and concepts might be covered on the exam?
The following is a non-exhaustive list of the tools and technologies that could appear on the exam. This list
is subject to change and is provided to help you understand the general scope of services, features, or
technologies on the exam. The general tools and technologies in this list appear in no particular order.
AWS services are grouped according to their primary functions. While some of these technologies will likely
be covered more than others on the exam, the order and placement of them in this list is no indication of
relative weight or importance:

- Compute
- Cost management
- Database
- Disaster recovery
- High availability
- Management and governance
- Microservices and component decoupling
- Migration and data transfer
- Networking, connectivity, and content delivery
- Security
- Serverless design principles
- Storage

#### AWS services and features
Analytics:

- Amazon Athena
- Amazon Elasticsearch Service
- Amazon EMR
- AWS Glue
- Amazon Kinesis
- Amazon QuickSight

AWS Billing and Cost Management:

- AWS Budgets
- Cost Explorer

Application integration:

- Amazon MQ
- Amazon Simple Notification Service (Amazon SNS)
- Amazon Simple Queue Service (Amazon SQS)
- AWS Step Functions

Business applications:

- Amazon Alexa
- Amazon Alexa for Business
- Amazon Simple Email Service (Amazon SES)

Blockchain:

- Amazon Managed Blockchain

Compute:

- AWS Batch
- Amazon EC2
- AWS Elastic Beanstalk
- Amazon Elastic Container Service (Amazon ECS)
- Amazon Elastic Kubernetes Service (Amazon EKS)
- Elastic Load Balancing
- AWS Fargate
- AWS Lambda
- Amazon Lightsail
- AWS Outposts

Containers:

- Amazon Elastic Container Registry (Amazon ECR)

Database:

- Amazon Aurora
- Amazon DynamoDB
- Amazon ElastiCache
- Amazon Neptune
- Amazon RDS
- Amazon Redshift

Developer tools:

- AWS Cloud9
- AWS CodeBuild
- AWS CodeCommit
- AWS CodeDeploy
- AWS CodePipeline

End user computing:

- Amazon AppStream 2.0
- Amazon WorkSpaces

Front-end web and mobile:

- AWS AppSync

Machine learning:

- Amazon Comprehend
- Amazon Forecast
- Amazon Lex
- Amazon Rekognition
- Amazon SageMaker
- Amazon Transcribe
- Amazon Translate

Management and governance: 

- AWS Auto Scaling
- AWS Backup
- AWS CloudFormation
- AWS CloudTrail
- Amazon CloudWatch
- AWS Compute Optimizer
- AWS Config 
- AWS Control Tower
- Amazon EventBridge
- AWS License Manager
- AWS Organizations
- AWS Resource Access Manager
- AWS Service Catalog
- AWS Systems Manager
- AWS Trusted Advisor
- AWS Well-Architected Tool 

Media services: 

- Amazon Elastic Transcoder

Migration and transfer: 

- AWS Database Migration Service (AWS DMS)
- AWS DataSync 
- AWS Migration Hub
- AWS Server Migration Service (AWS SMS)
- AWS Snowball
- AWS Transfer Family

Networking and content delivery:

- Amazon API Gateway
- Amazon CloudFront
- AWS Direct Connect
- AWS Global Accelerator
- Amazon Route 53
- AWS Transit Gateway
- Amazon VPC

Security, identity, and compliance:

- AWS Artifact 
- AWS Certificate Manager (ACM)
- Amazon Cognito
- AWS Directory Service
- Amazon GuardDuty
- AWS Identity and Access Management (IAM)
- Amazon Inspector
- AWS Key Management Service (AWS KMS)
- Amazon Macie
- AWS Resource Access Manager
- AWS Secrets Manager
- AWS Security Hub
- AWS Shield
- AWS Single Sign-On
- AWS WAF

Storage:

- Amazon Elastic Block Store (Amazon EBS)
- Amazon Elastic File System (Amazon EFS)
- Amazon FSx
- Amazon S3
- Amazon S3 Glacier
- AWS Storage Gateway