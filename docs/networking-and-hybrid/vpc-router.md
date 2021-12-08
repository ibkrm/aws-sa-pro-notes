### Characteristics
- **Virtual Router** within a VPC
- **Highly Available** - across all AZs in that region
- **Scalable** - no performance management required
- **Routes** traffic **between subnets**
    - also routes **EXTERNAL** networks **INTO** the **VPC**
    - also routes **VPC** into **EXTERNAL** networks
- Router has interface in every subnet - `subnet+1` address (**default GW** via **DHCP option set**)
- Controlled using **route tables**

![vpc-router](vpc-router.png)

### Route tables
- Every **VPC** is created with a **Maing route table** (RT)
    - also defaults for **every subnet** in the VPC
- **Custom route table** can be created and associated with subnets in the VPC which **removes the Main RT** from the subnet
- **Subnes** are **associated** with **One RT** (Main or Custom)
- **Main RT** should be left as it is and **Custom Route Tables** should be created for any customization
    - to ensure default association of subnet does not get default RT

- Route tables contain **routes** - **most specific** routes **first**
- RT's **can be associated with gateways**

