### Concepts
- **Clusters**
    - **EC2 Mode** 
        - Customer needs to maange availablity and scalablity of underlying EC2 instances for the cluster
    - **Fargate Mode** (<span style="color:orange;font-weight:bold">serverless</span>)
        - EC2 instances are managed by AWS
        - Fargate Shared Infrastructure
        - ENI's to be available from the VPC
        - Only pay for the container running in the cluster
- **Service**
    - Replicas of tasks
    - AutoScaling for the tasks
    - LoadBalancer configuration with target group
- **Task Definition**
    - **TaskRole** within task definition
    - **Container Definitions**
- **Container Definition**
    - Docker Image
    - Environment Variables
    - CPU and MEM
    - **CMD** and **ENRTYPOINT**
    - Ports
- **Docker Resgistry**
    - **ECR** or **DockerHub** to store docker imaages


### EC2 vs ECS (EC2) vs Fargate
- **Containers** **==>** ECS
- **Large** workload - <span style="color:orange;font-weight:bold">prices conscious</span> - **EC2 Mode**
- **Large** workload - <span style="color:orange;font-weight:bold"></span> - **Fargate**
- <span style="color:orange;font-weight:bold">Small/Burst</span> workloads - **Fargate**
- <span style="color:orange;font-weight:bold">Batch /Periodic</span> workloads - **Fargate**