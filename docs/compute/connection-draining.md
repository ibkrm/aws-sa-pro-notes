<!-- <h2 style="color:green">Connection Draining </h2> -->
<!-- <h2 style="color:green">why </h2> -->

### Connection Draining
- **Only supported in Classic Load Balancer (CLB)**
- gracefully disconnect the connections (ASG/EC2)
- allows in-flight request to complete
- <span style="color:red">timeout value</span>: 1s - 3600s (<span style="color:green">default</span>: 300s)
- <span style="color:orange;font-weight:bold">Timeout does not apply to failed health check</span>
- applies when instance taken out of ASG - manually or ASG activities
    - <span style="color:red;font-weight:bold">InService: Instance deregistraiton currently in progress</span>   
    - AS waiting for all connections to complete of timeout - whichever occur first

### Registration Delay 
- **Supported in ALB, NLB, GWLB - defined on the target group**
- stop sending requests to deregistration targtes
- existing connections can continue until they complete naturally
- enabled by default with value 300s
- 0-3600s
---
**X-Forwarded-For** and **Proxy protocol** are two alternative versions of gaining visibility of original client IP address when using proxy servers or load balancers


### X-Forwarded-For
- Set of **http/https headers** (layer 7)
- Header is appended or added by proxies/LB
- **Http Header** -> `X-Forwarded-For: client,proxy1,proxy2`
- **Client** is the left most in the list
- Supported in CLB and ALB but <span style="color:red;font-weight:bold">NOT SUPPORTED IN NLB</span>

### PROXY protocol
- Proxy protocol works at **Layer 4**
- TCP header works with layer 4
    - also works with **http/https**
- v1 (human readable) - **CLB** || v2 (binary encoded) - **NLB**
- <span style="color:red;font-weight:bold">Not supported in ALB</span>
- **Use Case** -> unbroken https encryption between client and server (`tcp listener`)
