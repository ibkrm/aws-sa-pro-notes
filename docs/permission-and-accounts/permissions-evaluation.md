### Overview
|  | |
|:---:|:---: |
|**Explicit Deny**|<span style="color:red;font-weight:bold">Check for Explicit Deny</span></br>**Procced with SCP if there is no explicit deny**|
|**SCP**|<span style="color:#FF00FF;font-weight:bold">Check for any SCP policy and check for Allow</span></br>**Procced if SCP allows**|
|**Resource Policies**|<span style="color:#FF00FF;font-weight:bold">Check for Allow and execute if it is allowed</span></br>**Procced if Allow is not there**|
|**Permission boundaries**|<span style="color:#FF69B4;font-weight:bold">Check for disallowed action form boundary policy</span></br>**Procced with Session policy if no permission boundary**|
|**Session Policies**|<span style="color:orange;font-weight:bold">Check for Session Policy</span></br>**Procced with Identity Policy if allow**|
|**Identity Policies**| <span style="color:green;font-weight:bold">Check for Allow or no Allow</span></br>**Procced with resource execution**|

### Same Account
![permissions-evaluations-same-account](permissions-evaluations-same-account.png)

### Different Accounts
![permissions-evaluations-different-accounts](permissions-evaluations-different-accounts.png)
