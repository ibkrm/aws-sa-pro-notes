### Overview

- **Authentication**, **Authorization**, and **user management** for web/mobile apps
- **USER POOLS** 
    - **SIGN-IN** and get a JSON Web Token (**JWT**)
    - Provides user directory management and profiles
    - Sign-up and sign-in (customisable web UI), MFA and other security features

</br>

![cognito-user-pools](cognito-user-pools.png)

- **IDENTITY POOLS**
    - Allow you to offer access to **Temporary AWS Credentials**
    - <span style="color:orange;font-weight:bold">Unauthenticated identities</span> - Guest Users
    - <span style="color:green;font-weight:bold">Federated Identities</span> - **SWAP** - Facebook, Google, Twitter, SAML2.0 & User Pool for short term AWS Credentials to access AWS Resources

</br>

![](cognito-identity-pools.png)

### User Pools + Identity Pools
![](cognito-user-identity-pools.png)