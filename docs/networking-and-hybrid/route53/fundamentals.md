### Basics
Amazon Route 53 is a highly available and scalable cloud Domain Name System (DNS) web service. It provides following features

1. **Register Domains**
   1. 
2. **Hosted Zones - managed nameserers**
   - **Zone files** in AWS
   - Hosted on four managed name servers
   - Public Hosted Zone
   - Private Hosted Zone - linked to **VPCs**
   - RecordSets - records within hosted zone


### DNS Record Types

- **Nameserver (NS)**
   
- **A and AAAA Records**
    - A record maps to ipv4
    - AAAA record maps to ipv6

- **CNAME Records**
    - cannot point directly to other names
    - can only point to the name

- **MX Records**
    - important for email
    - priority and value (mail || mail.other.domain)
    - MX query
  
- **TXT Records**
    - additional text data to the record
    - Query TXT for the validation
  
#### TTL - Time To Live
- Resolver cached for TTL no. of seconds
   - also non-authoriative answer
