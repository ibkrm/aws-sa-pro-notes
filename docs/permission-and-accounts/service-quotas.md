### Key Points
- Defines the limit on how many of AWS services can run
- Each service has a **default per-region** quota
    - some services can be **per account**

- Most service quotas **can be increased** as needed
    - some services quota **cannot be changed** like **5000 IAM user/account**
    - <span style="color:orange;font-weight:bold">for IAM users > use identity provider</span>

- **Higher increases** results in **more process and time** needed

### Important Links
- [Service endpoints and quotas](https://docs.aws.amazon.com/general/latest/gr/aws-service-information.html)
- [Service Quotas Console](https://console.aws.amazon.com/servicequotas/home?region=us-east-1#!/) - also request change for quotas
- [Service Quotas request templates](https://docs.aws.amazon.com/servicequotas/latest/userguide/organization-templates.html) - can be applied for accoutns in AWS organizations (reduced )
- [AWS cli for service quotas](https://awscli.amazonaws.com/v2/documentation/api/latest/reference/service-quotas/list-service-quotas.html)
- [Service Quotas and Amazon CloudWatch alarms](https://docs.aws.amazon.com/servicequotas/latest/userguide/configure-cloudwatch.html)
