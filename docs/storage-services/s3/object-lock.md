### Overview

- Object Lock enabled on `new` buckets 
    - existing bucket needs to go via AWS request support
    - `versioning` is enabled by default and once object lock is enabled, `versioning` cannnot be supspended or diabled the object lock
- **WORM** - Write Once Read Many
    - <span style="color:red;font-weight:bold">No Delete, No Overwrite</span>
-  Requires versioning - `invdividual versions` are locked
-  Can have **both**, **one or the other**, or <span style="color:red;font-weight:bold">none</span>
      -  **Retention Period**
      -  **Legal Hold**
- A bucket can have **default Object Lock Settings**

### Retention
- Specify **DAYS** & **YEARS** - A Retention Period

1. **COMPLIANCE** - <span style="color:red;font-weight:bold">Can't be adjusted, deleted, overwritten</span>
    - <span style="color:orange;font-weight:bold"> not even by the root user</span>
    - <span style="color:orange;font-weight:bold">until the rentention period expires</span>
    - for compliance - financial records

2. **GOVERNANCE** - special **pemissions** can be granted <span style="color:green;font-weight:bold">allowing lock settings to be adjusted</span>
    - `s3:BypassGovernanceRetention` - access
    - `x-amz-bypass-governance-retention:ture`
    - accidental deletion, testing mode for compliance mode

### Legal Hold
- Set on a **object version** - either ON or OFF
    - no retention
- <span style="color:red;font-weight:bold">NO Deletes or Changes</span> until removed
- `s3:PutObjectLegalHold` is required to add or remove
- Prevent accidental deletion of critical object versions

</br>

![s3-object-lock](../images/s3-object-lock.png)