### Stateful vs Stateless Firewalls
|Stateless|Stateful|
|:---:|:---:|
|Explicit inbound and outbound for any traffic|In-built intelligence based on the request|
|Inbound and outbound rule for both client and server| Outbound rules are automatically determined and allowed like **ephemeral port**|
|Outbound and inbound for server for software update| Inbounds rules are automatically determined from the request like **ephemeral port**|

### NACL
A **network access control list** (ACL) is an optional layer of security for your VPC that acts as a firewall for controlling traffic in and out of one or more subnets.

- **STATELESS** - request and response are viewed as different entity
- NACL filter traffic crossing the subnet bondary **INBOUND or OUTBOUND**
- It does not affect traffic within the subnet
- Each NACL comprises of 2 set of rules -  **Inbound Rules** and **Outbound Rules**
- Each rule within NACL can explicitly **ALLOW** or **DENY** traffic based on **DST IPs/CIDR or DST Port or Protocols** - no logical resources
- Rules within NACL are processed in order. **Lowest rule number** gets priority and **\*** can be used for **implicit deny** if no match is found for the destination traffic.
- Can be used with **Security Group** to add **explicit Deny**
- **Single NACL** can be associated  with **multiple subnets**

</br>
#### Default NACL
- **VPC** is created with default **NACL**
- Inbound and Outbound Rules have the **implicit deny(*)** and **ALLOW** ALL rule
    - results in all traffic is **allowed** and the NACL has no effect

#### Custom NACL
- **Custom NACLs** can be creaeted for a specific VPC
    - **not associated** with any **SUBNETS** initially
- Default inbound and oubound rules have **implicit(*) DENY**
    - results in **all traffic DENIED**

### Security Groups
- **STATEFUL** - detect response traffic automatically
- **Allowed** (IN or OUT) **request** = **allowed response**
- **NO Explicit DENY** .. only ALLOW or implicit DENY
    - <span style="color:red;font-weight:bold">can't block specific bad actors</span>
- Supports **IP/CIDR** + **logical resources**
    - including other **security groups** AND itself
- Attached to **ENI's** not instances
- Comprises of **Inbound and Outbound** rules
- Self referencing **SG rules** - nodes talking to each other in cluster mode
