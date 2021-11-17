<!-- <h2 style="color:green">Connection Draining </h2> -->
<!-- <h2 style="color:green">why </h2> -->

### Connection Draining
- only supported in Classic Load Balancer (CLB)
- gracefully disconnect the connections (ASG/EC2)
- allows in-flight request to complete
- <span style="color:red">timeout value</span>: 1s - 3600s (<span style="color:green">default</span>: 300s)
- does not apply to failed health check
- applies when instance taken out of ASG - manually or ASG activities
    - <span style="color:red">InService: Instance deregistraiton currently in progress</span>   
    - AS waiting for all connections to complete of timeout - whichever occur first
---

### Registration Delay 
- supported in ALB, NLB, GWLB - defined on the target group
- stop sending requests to deregistration targtes
- existing connections can continue until they complete naturally
- enabled by default with value 300s
- 0-3600s
---

### X-Forwarded-For 
- set of http/https headers (layer 7)
- header is appended or added by proxies/LB
- http header -> X-Forwarded-For: client,proxy1,proxy2
- client is the left most in the list
- Supported in CLB and ALB (not supported in NLB)

### PROXY protocol
- proxy protocol works at layer 4
- tcp header works with layer 4
- also works with http/https
- v1 (human readable) - CLB || v2 (binary encoded) - NLB
- not supported in ALB
- use case -> unbroken https encryption between client and server

### Gateway Load Balancer - GWLB
- run and scale 3rd party appliances
- examples - firewalls, intrusion detection and prevention systems
- inbound and outbound traffic (transparent inspection an protection)
- GWLB Endpoints ->  traffic enters/leaves via these endpoints
- GWLB -> balances accross multiple backend appliances
- GENEVE protocol -> tunneling protocol (between GWLB and backend instances)
- Traffic and metadata is tunnelled using GENEVE protocol
