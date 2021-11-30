### AWS cloudformation
- **IaaS**
- **logical resources** => **physical resources** 
- **Stacks**
- **non-portable templates**
    - hardcoded s3 bucket name or AMI for EC2 instances
- **template parameters** - accept inputs from CLI/API/Console
    - when a stack is created or updated
- **psuedo paramters** 
    - AWS make available parameters
    - can be used even without specifying in template parameters - e.g- AWS::Region, AWS::AccountId, AWS::StackName, AWS::StackId
- **intrinsic functions** 
    - [aws refrence](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/intrinsic-function-reference.html)

- **template mappings**
  - key value mappings
  - one key or top & second level
  - !FindInMap instrinsic function
  - improves template portability

- **conditions**
  - evaluated to either **TRUE** or **FALSE**
-  **depends on**
  - in-built dependency order/tree (VPC => subnet => EC2) determined by CloudFormation
  - explicit defined control dependency order 
- **wait conditions**
    - **cloudformation signal**
        - configure cloudformation to hold
        - wait for 'X' no. of success signals
        - wait for timeout (12 hr max)
        - If success signals received .. **CREATE_COMPLETE**
        - if failure signal received.. creation fails
        - if timeout is reached .. creation fails
        - **CreationPolicy** or **WaitCondition**
    - **CreationPolicy**
- **nested stacks**
  - overcome the **500 Resource Limi** of one stack
  - **modular templates** ... **code reuse**
  - make the installation process easier
    - ..nested stack created by the root stack
  - :rotating_light: <span style="color:red;font-weight:bold">use only when everything is lifecycle linked</span>

- **cross-stack references**
    - outputs are normally not visible from other stacks
    - nested references can reference them..
    - outputs are **exported** .. **making them visible from other stacks**
    - Exports must have a unique name in the region
    - **Fn::ImportValue** can be used instead of **Ref**

- **stack sets**
    - deploy CFN stacks across **many accounts** & **regions**
    - StackSets are **containers** in an **admin account**
        - ...contain **stack instances**.. which **reference stacks**
    - **Stack instances** & **stacks** are in `target accounts`
    - **Each stack** = 1 region in 1 account
    - :rotating_light: Security = <span style="color:red;font-weight:bold">self-managed or sevice-managed</span>
    - **keys and concepts**
        - concurrent accounts -  more conncurent account=>faster the deployment
        - failure tolerance - no. of failed individual stacks to determine the whole set to be failed
        - retain stacks - to retain stack in aws account when the set it deleted
    
    - **scenarios**
        - Enable AWS Config
        - AWS Config Rules - MFA, EIPS, EBS Encryption
        - Create IAM Roles for cross-account access

- **deletion policy**
    - **DeletionPolicy**
    - By default, `resources` associated with CFT is deleted when the templete is deleted = which can cause data loss 
    - **Delete** (Default), **Retain** or (if supported) **Snapshot**
    - Snapshot supported by 
        - EBS volume, ElastiCache, Neptune, RDS, Redshift
        - Snapshots continue on pst Stack lifetime - you have to clean up ($$)
    - <span style="color:red;font-weight:bold">ONLY APPLIES TO DELETE .. NOT REPLACE</span>
        - when resource is deleted from the template and cft is redeployed
        - when the whole template is deleted
- **stack roles**
    - CFN uses the **permissions** of the **logged in identity**
    - requires **permissions for AWS**
    - CFN can **assume a role** to **gain the permission**
    - Lets you implement **role seperation**
    - The identity creating the stack only need **PassRole** and **doesnot need resource permissions**
    
- **CloudFormationInit & cnf-init**
    - Simple configuration management system
    - Configuration **directives** stored in template
    - **AWS::CloudFormation::Init** part of logical resource
    - Procedural - **HOW** (User Data)
    - ... vs **WHAT** (cfn-init) - idompotent
    - **cnf-init** helper script - installed on EC2 OS (make it so)

- **cnf-hup**
    - **cfn-hup** helper is a daemon which can be installed 
    - .. it **detects changes** in **resource metadata**
    - .. **running configurable actions** when a **change is detected**.
    - UpdateStack => update config on EC2 instances

- **ChangeSets**
    - Change Sets let you preview changes (**A Change Set**)
        - ..multiple different versions for a stakc (lots of change sets)
    - Chosen changes can be applied by **executing** the change set 

- **CustomResources**
    - logical resources in a tempalte
    - **create, update and delete** physical resources
    - 