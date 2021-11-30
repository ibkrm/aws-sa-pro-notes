## AWS Shield
- Provides AWS resources with **DDoS protection**



|AWS Shield Standard| AWS Shield Advance|
| :---: | :---: |
|Free with **Route53** and **CloudFront** | **$3000/month/organization** which also supports - **EC2, ELB, Global Accelerator** in addition to **Cloudfront & R53**|
|Protect against **Layer 3** and **Layer 4** **DDoS** attacks| **same**  |
|| Provides **24/7 (365 days)** **advance response team** to deal with DDoS atack|
|| **Financial Insurance** for any increased AWS cost incurred by the attack |


## AWS WAF
**Web Application Firewall**

- **Layer 7** (HTTP/s) Firewall
- Protect against complex Layer 7 attacks/exploits
- **SQL Injections, Cross-Site Scripting**, Geo Blocks, Rate Awareness
- Web Access Control List (**WEBACL**) integrated with **ALB, API Gateway and CloudFront**
    - **WAF** provides **WEBACL** 
    - **Rules** are added to **WEBACL** and **evaluated** when traffic **arrives**