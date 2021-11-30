## AWS Inspector
- Scans **EC2** instances and the **instance** OS
    - scans for **vulnerabilities** and **deviations** against best practice
- Assessment varying period.. 15mins, 1 hours, 8/12 hours or 1 day
- Provides a **report of findings** ordered by priority
- Network Assessment (**Agentless**)
- Network + Host Assessment (**Agent**)

- Rules packages determine what is checked
- Network Reachibility package (**no agent required**)
     - agent can provide  **additional OS visibility**
- Check reachibility end to end.
    - EC2, ALB, DX, ELB, ENI
    - IGW, ACLs, RT's, SG's, Subnets, VPCs, VGWs & VPC Peering
- Network Reachability package findings
    - `RecognizedPortWithListener`: exposed to public and OS listening to the port
    - `RecognizedPortNoListener`: exposed to public but OS not listening
    - `RecognizedPortNoAgent`: exposed but no agent to confirm if OS is listening
    - `UnrecognizedPortWithListener`: unrecognized port exposed and OS listening to the port

- **Host Assessment** package (**agent required**)
    - **CVE** - Common Vulnerabilities & Exposures
    - **CIS** benchmarks - Center for Internet Security
    - **Security best practices** for Amazon Inspector
    