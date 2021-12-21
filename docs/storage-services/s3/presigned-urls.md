### S3 Presigned URL
Presigned URL's are a feature of S3 which allows the system to generate a URL with access permissions encoded into it, for a specific bucket and object, valid for a certain time period.

- **Temporary acces** to specific S3 object
- **Presigned URL** is generated using credentials from **IAM user/role** 
    - access to object is temporary
    - access to object is also determined by access assigned to user/role used to generate the URL(**current permission**) 
- Can create a URL for an object you have <span style="color:red;font-weight:bold">no access too</span>
    - can create a URL for **non-existing object** as well
- <span style="color:red;font-weight:bold">Don't generate with a role..</span> URL stops working when **temporary credentials expire** (role session token has short-term validity) - use **long-term indentity like IAM user**


**Using CLI**
> IAM creds from role could expire before the expiry time in the presigned URL

[aws s3 presign command](https://docs.aws.amazon.com/cli/latest/reference/s3/presign.html)
`aws s3 presign s3://<s3-bucket>/<object-key> --expires-in <time-in-seconds-to-expire>`
