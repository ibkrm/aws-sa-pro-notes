### IPv4

**Private IPv4** (RFC1918) are translated into **Public IPv4** via **NAT**
> NAT=Network Address Translation

Services (**EC2 instances**) never have public IPv4 Addressing configured on them within a VPC .. handled by the IGW

**IPV4 Address Space** - <span style="color:green;font-weight:bold">Total: 4,294,967,296</span>
|CLASS A| CLASS B| CLASS C|CLASS D|CLASS E|
|:---:|:---:|:---:|:---:|:---:|
||||||

### IPv6
- All **IPv6 addresses** in use within AWS are **publicly routable**
- <span style="color:red;font-weight:bold">NAT is not used for IPv6</span>
- <span style="color:green;font-weight:bold">Egress Only Internet Gateway for outgoing traffic only</span> 
- Enable on the VPC
    - Either AWS provides the range `/56` for the VPC
        - and subnets pick the CIDR rannge within VPC CIDR range
    - OR bring your own IPv6 range
- Routing for **IPv4** and  **IPv6** are handled seperately
    |Destination|Target|
    |:---:|:---:|
    |10.16.0.0/16|local|
    |**2600::ff18:8e1:2200::/56**|**local**|
    |0.0.0.0/0|IGW|
    |**::/0**|**EG-IGW**|

**Considerations**

- IPv6 can be added **while creating** a VPC/Sunets
    - Or addressing **can be migrated** to IPv6
- Add **VPC Range**, Add **subnet range(s)**
- Add **routes** & appropriate **gateway(s)**
- Configure **IPv6 on Services**
- Be aware of which services **support IPv6** vs **NOT**
    - like **AWS PrivateLink**