
### Overview
- Boundaries can be applied to **IAM user and roles**
- IAM permission boundaries does not affect **RESOURCE POLICIES** (only **IDENTITY POLICY**)
- Permission boundaries don't GRANT any access but define maximum **permissions** an  **identity** can receive
 

### Use Cases
- Delegation Problems
    - IAM administrator permissions
        - apply permission boundary policy for user 
        - allow adminstration to update user with the user boundary policy
        - does not allow to modify it owns policy but also does not allow to modify user with no user boundary policy attached