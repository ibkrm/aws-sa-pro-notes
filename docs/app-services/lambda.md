### Overview
- **FaaS** - Function-as-a-Service
    - piece of code that lambda runs
- RunTime Environment - python3.8, node12
- Define **Memory** for lambda and lambda automatically defines CPU for the function
    - **128 MB and 10,240 MB** in 1-MB increments
    - **1,769 MB** = 1vCPU
- **Supported packages** - traditionally only supported **ZIP**
    - **ZIP**
    - **Lambda Container Images**
        - Lambda Runtime API - in container image
        - supports already built docker image from CICD
        - Runtime Interface Emulator (**RIE**) - for local testing
- **Storage**
    - **512 MB** available as `/tmp` - ephemeral
    - `EFS` can be mounted for persistent storage
- **Execution Timeout** - 15 mins (900s)
- **Common Uses**
    - S3 Events -> Lambda
    - DynamoDB Streams -> Lambda
    - **EventBridge/CWEvent** -> Lambda
    - **API Gateway** -> Lambda
    - **Kinesis** -> Lambda

#### Networking and Security
- **Public Lambda** 
    - can acccess internet and public services
    - no access to VPC based services unless security control allow external access
- **Private Lambda**
    - runs **inside VPC**
    - can access services inside VPC
    - cannot access public services unless configuration is properly done
- **ENI** is configured for unique set of subnet and SGs instead of **ENI** per lambdas
- **Execution** IAM role for lambda determines what access lambda has when the function is being executed
- **Resource Policy** - policy controls/determines which services can invoke lambdas
    - could not be updated via **Console**
- **Cloudwatch**
    - **Logs** - `/aws/logs/function-name`
        - permission via Execution role
    - **Metrics** - invocations,error rate, success rate,latency
    - **X-Ray** - for distributed tracing

### Invocations, Latency, Destination
- **Synchronous** - retries/errors handled by client
- **Asynchronous** - reties automated by lambda
- **Event Source Mapping** - typically used on streams or queues (Kinesis, DynamoDB streams, SQS)
    - **Event Source Mappings** read/poll from stream or queue and deliver Event Batches to lambda
    - **Event Source Mappings** leverage execution IAM role for interacting with streams or queues
- **DLQ Failed Event** can be sent SQS Queues or SNS topics for further processing

- **Cold Start** - setting up the environment for the lambda execution
- **Warm Start** - context is reused to execute the function lambda
- **Provisioned Concurrency** - reduce the no. of cold starts

### Lambda Versions
- Functions can be published .. **immutable version**
- Each version ==> **Code** + **Configuration** of the lambda function
- **Immutable** with its own unique **ARN**
- **$LATEST** = > points to the latest version

### Lambda Aliases
- An **Alias** is a pointer to a **function version**
- Has unique **ARN***
- Can be updated and point to different versions of lambda
- Can be used to **PROD/DEV**, **BLUE/GREEN** and **A/B testing**
- **Alias Routing** - split traffic between versions of lambda
    - 40 to v1 and 60 to v2

### Lambda Layers
- Large libraries or dependencies can be deployed as library
- This layers(libraries) can be imported in the lambda function and these libraries are not part of deployment pacakge

### Lambda and ALB
- **ALB - TargetGroup -> Lambda**
- Lambda needs to parse the ALB request and respond with the response that ALB is expecting
- <span style="color:red;font-weight:bold">Mult-Value Headers</span>
    - [requests with multi-value headers](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/lambda-functions.html#multi-value-headers)
    - multi-value headers needs to be enabled to get all the parameters sent by the client 