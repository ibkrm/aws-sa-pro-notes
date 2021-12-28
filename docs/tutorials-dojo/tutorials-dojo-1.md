### System manager parameter store servie role and service linked role
https://docs.aws.amazon.com/systems-manager/latest/userguide/setup-service-role.html

If you plan to use Systems Manager to manage on-premises servers and virtual machines (VMs) in what is called a hybrid environment, you must create an IAM role for those resources to communicate with the Systems Manager service.

#### Direct Connect Gateway for connection multi region 
You can use an AWS Direct Connect gateway to connect your AWS Direct Connect connection over a private virtual interface to one or more VPCs in your account that are located in the same or different Regions

With Direct Connect Gateway, you no longer need to establish multiple BGP sessions for each VPC; this reduces your administrative workload as well as the load on your network devices.

#### Scheduled RDS backup

#### you can associate a VPC from one account with a private hosted zone in a different account
you first must authorize the association ..After you authorize the association, use the account that created the VPC to submit an `AssociateVPCWithHostedZone` request.

#### AWS Systems Manager Patch Manager automates the process of patching managed instances with security-related updates.
 For Linux-based instances, you can also install patches for non-security updates

#### The master account of an organization can turn off Reserved Instance (RI) sharing for member accounts in that organization.
 This means that Reserved Instances are not shared between that member account and other member accounts.

#### Central DNS management with one AWS account 
https://aws.amazon.com/blogs/security/simplify-dns-management-in-a-multiaccount-environment-with-route-53-resolver/
- Share VPC using RAM and VPC peering between each accounts
- Associate the VPCs from other accounts with the hosted zone 
  
#### Lambda@Edge to customize the content  that Cloudfront delivers to change the request and response
- like redirect traffic to closest region

#### AWS Systems Patch Manager
- automates the process of patching managed instances with security-related updates. For Linux-based instances, you can also install patches for non-security up
- Patch Manager uses patch **baselines**, which include rules for auto-approving patches within days of their release, as well as a list of approved and rejected patches.
- A patch group is an optional means of organizing instances for patching. - **different environment** or **different OS**
- <span style="color:red;font-weight:bold">RUN command can be used for common administrative tasks and perform ad hoc configuration changes at scale</span>
- <span style="color:red;font-weight:bold">Maintainence Windows - antoher option but comes with a lot of configuraiton and effort to implement</span>

#### Public read access needs to be enabled for static website
When you configure an Amazon S3 bucket for website hosting, you must give the bucket the same name as the record that you want to use to route traffic to the bucket

#### Amazon Simple Workflow Service (SWF) is a web service that makes it easy to coordinate work across distributed application components.
[use cases that can be solved with Amazon SWF](https://aws.amazon.com/swf/faqs/#:~:text=Use%20case%20%231,without%20causing%20disruptions.)

#### ALB health checks protocol - http/https

#### Amazon Rekognition can store information about detected faces in server-side containers known as collections.
 You can use the facial information that's stored in a collection to search for known faces in images, stored videos, and streaming videos

#### Storage Volume Gateway (TAPE) - use the current data store not the archived one


#### Amazon Guardduty is primarily used as a threat detection service
that continuously monitors for malicious or unauthorized behavior to help you protect your AWS accounts and workloads.

#### AWS Shield Advanced service is most suitable to prevent DDoS attacks in your AWS resource

#### GP2 storage credit systems - burst mode and exhaustion of credits during high traffic
**Provisioned IOPS SSD (io1 and io2) volumes** are designed to meet the needs of I/O-intensive workloads, particularly database workloads, that are sensitive to storage performance and consistency.

#### AWS Resource Access Manager (AWS RAM) enables you to share specified AWS resources that you own with other AWS accounts.
To enable trusted access with AWS Organizations:
- From the AWS RAM CLI, use the `enable-sharing-with-aws-organizations` command.
- Name of the IAM service-linked role that can be created in accounts when trusted access is enabled: *AWSResourceAccessManagerServiceRolePolicy*. 

#### Route53 Alias Records
To route domain traffic to an ELB load balancer, use Amazon Route 53 to create an alias record that points to your load balancer. 
- An alias record is a Route 53 extension to DNS. It's similar to a CNAME record, but you can create an alias record both for the root domain, such as example.com, and for subdomains, such as www.example.com. (You can create CNAME records only for subdomains). 
- For **EC2 instances**, always use a Type A Record without an Alias. 
- For **ELB, Cloudfront and S3**, always use a Type A Record with an Alias and 
- finally, **for RDS**, always use the CNAME Record with no Alias.

#### AWS SMS 
https://docs.aws.amazon.com/server-migration-service/latest/userguide/server-migration.html

#### Amazon Route 53 DNSSEC provides data origin authentication and data integrity verification for DNS and can help customers meet compliance mandates, such as FedRAMP.
https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/dns-configuring-dnssec.html

#### AWS strongly recommends that you don't attach SCPs to the root of your organization without thoroughly testing the impact that the policy has on accounts. Instead, create an OU that you can move your accounts into one at a time, or at least in small numbers, to ensure that you don't inadvertently lock users out of key services.

#### Cloudsearch ??? 

#### Cloudtrail --> include-global-service-events and is-multi-region-trail

#### DNS attributes in VPC

| Attribute | Description | 
| --- | --- | 
| enableDnsHostnames |  Determines whether the VPC supports assigning public DNS hostnames to instances with public IP addresses\. If both DNS attributes are `true`, instances in the VPC get public DNS hostnames\. The default for this attribute is `false` unless the VPC is a default VPC or the VPC was created using the VPC console wizard\.  | 
| enableDnsSupport |  Determines whether the VPC supports DNS resolution through the Amazon provided DNS server\. If this attribute is `true`, queries to the Amazon provided DNS server succeed\. For more information, see [Amazon DNS server](VPC_DHCP_Options.md#AmazonDNS)\. The default for this attribute is `true`, no matter how the VPC is created\.  | 