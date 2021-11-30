# CICD  
**Continuous Integration and Continuous Delivery**
### AWS CodeCommit
- similar to gihub
- authentication - iam user 
- authorization - iam identity policy 
- notifications  - on events
- triggers - on events

### AWS CodePipeline
- **CD** tool 
- Orchestration tool for code, build, test and deploy
    - controls the flow from source through build and deployment
- Pipelines are built form **STAGES**
- **STAGES** can have sequential or parallel **ACTIONS**
- Movement between stages can require **manual approval**
- Artifacts can be **loaded into an action**, and **generated from an action**
- **Stage Changes** => Event Bridge (eg. success, failed, cancelled)
- **CloudTrail** or **Console UI** to view/interact

### AWS CodeBuild
- Code **Build** as a service - fully managed
- **Pay** for the **resource consumed** during **builds**
- Alternate to part of jenkins functionality
- Used for **builds and tests**
- Uses **docker** for build environment, can be customized
- Integrates with **AWS Services**: KMS,IAM, VPC, CloudTrail, S3...
- **Sourced from** -> Github or CodeCommit or CodePipeline or S3
- Customised via `buildspec.yml` file (root of source)
- **Logs** => CloudWatch, S3
- **Metrics** => CloudWatch
- **Events** => EventBridge (event-driven response)
- **supported languages** - java,ruby,python,go,.net,php,node.js
- **PHASES**
    - **install** - install packages in build environment
    - **pre_build** - sign-in or install dependencies
    - **build** - commands for the build process
    - **post_build** - package things up, push docker image, explicit notifications
    - `also support environment variables - shell, variables, parameter-store, secrets-manager`
    - `artifacts - where to put`

### AWS CodeDeploy
- Code **Deployment** as a service
- **Alternatives** - jenkins, ansible, chef, puppet, cloudformation
- Deploy code.. not resources
- Deploys to **EC2, On-premises, Lambda and ECS**
- Also deploys web, configuration, EXE files, Packages, Scripts, media and more ..
- CodeDeploy integrates with AWS services and **AWS Code\* tools**
- For **On-premise and EC2** - Codedeploy **agent** needs to be installed
- `Appsec.yml` - yaml or json [reference link](https://docs.aws.amazon.com/codedeploy/latest/userguide/reference-appspec-file-structure.html)
    - **Files** (EC2/On-premise)
    - **Permissions** (EC2/On-premise)
    - **Resources** (ECS/Lambda)
    - **Hooks** (ECS/Lambda/EC2/On-premise) - [reference link](https://docs.aws.amazon.com/codedeploy/latest/userguide/reference-appspec-file-structure-hooks.html)
        - Lifecycle hooks are different for each type of deployments.
