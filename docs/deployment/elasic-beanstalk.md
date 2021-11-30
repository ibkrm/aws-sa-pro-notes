## Elastic Beanstalk
- **PaaS** - Platform as a service 
- **Developer Focused** - not end user
- Great for smaller development teams
- High level - **Managed Application Environment**
- **User Provide code** and **EB handles the environment**
- Focus on code, **low infrastructure overhead**
- **Fully customisable** - uses AWS products under the covers
- **Requires application changes** .. does not come for free
- <span style="color:red;font-weight:bold">Databases OUTSIDE of Elastic BeanStalk   </span>
 - <span style="color:red;font-weight:bold">DB in env are lost if env is deleted</span> 

 ### EB - Platforms
- **Built-in languages**
    - Go, java, java + tomcat, .NET Core(linux) & .NET (Windows)
    - nodejs, python, pho, ruby
- **Docker**
    - single container docker
    - multi container docker (ECS behind the scene)
    - preconfigured docker for unsupported runtime (glassfish java8)
- **Cutom**
    - use **packer** to create custom platform

### EB - Application
- Collection of things relating to an application
- **Versions** of application is stored in S3 and sourcable (zip or war)
- **Environments** 
    - containers of infrastructure running a specific versions
    - each environment has it own **CNAME**
    - **CNAME Swap** to enable blue/green deployment
    - **web server tier** - usually service traffic from **load balancers** 
    - **worker tier** - processing requests from queue like **SQS**
   

### EB - Deployment Policies
- **All at once** -  deploy to all at once, brief outage
- **Rolling** - deploy in rolling batches
- **Rolling with additional batch** - as above, with new batch to maintain capacity during the process
    - 150 % of capacity depending on the configuration
    - both versions serving traffic at one point
- **Immutable** - all new instances with new version
    - create another set of ASG
    - delete the old ASG
- **Traffic Splitting** - fresh instances, with a traffic split (A/B testing)

### EB and RDS 
- RDS provisioned with EB is associated with EB and will be deleted once EB environment is deleted.
- Different data in different environment (different RDS)
- environment properties: `RDS_HOSTNAME`, `RDS_PORT`, `RDS_DB_NAME`, `RDS_USERNAME`, `RDS_PASSWORD`
- RDS provisioned outside EB should configure above properties as environemnt variables
- **Steps to decouple exsiting RDS**
    - create snapshot of RDS
    - enable termination protection
    - create another EB environment with same verison without RDS
    - ensure the EB new environment can connect to RDS
    - make the CNAME switch from old to new environment
    - delete the old EB environment
    - clean up the failed cloudformation stack and retain the RDS created via CFN stack 

### EB customisation
- [link to extensions files](https://github.com/awsdocs/elastic-beanstalk-samples/tree/master/configuration-files)
- extension folder - `.ebextensions`
    - config file (yaml or json) ends with `.config`

### EB & HTTPS
- apply SSL cert to the load balancer directly via EB console
- **OR** apply via `.ebextensions/securelistener-[alb][nlb].config`
```yaml
option_settings:
aws:elbv2:listener:443:
    ListernerEnabled: 'true'
    Protocol: HTTPS
    SSLCertificateArns: arn:....
```

### EB cloning
- Clone an existing env to another
- Update the new env once the cloning is complete
- RDS data is not copied during cloning
- Changes outside the EB will not be copied

### EB and Docker
- **Single container** application
    - Dockerfile
    - docker-compose
- **Mutiple container** applications
    - ECS cluster
    - EC2 instances provisioned in the cluster and ELB for HA
    - Dockerrun.aws.json (V2) file in root of application source code
    - Docker image will have to be stored in docker registry like ECR