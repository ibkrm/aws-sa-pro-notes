### S3 Object encryption
Encryption at-rest

| Client-Side| Server-side|
|:---:|:---:|
|Encrypted data is sent from client to S3| Data is only encrypted from s3 endpoint. Data is not encrypted (at-rest) before uploading to s3 endpoint|
|Key management is entirely done by customer| Key management is partially/entirely done by S3 (AWS)|

**Server-Side encryption**

- **SSE-C** - customer-provided keys
    - customer uploads object with keys
    - s3 encrypts and decrypts before uploading or downloading the objects
    - > reduces the overhead of encryption and decryption on the customer side 
- **SSE-S3** - amazon S3-managed keys
    - customer uploads object 
    - S3 uses master key to create a unique Key to encrypt the object - **AES256**
    - S3 then encrypt the unique Key and the original unique Key is discarded
    - both encrypted key and object is now stored in the S3
    - customer has no control over master and encrypted keys
- **SSE-KMS** - customer master keys (**CMKs**) stored in AWS KMS service
    - Segregation of duties - sysops vs admin

**Bucket Default Encryption**
- set `DEFAULT=AES256` if `x-amz-server-side-encrypion` is not provided
- use bucket policy to enforce object encryption for the bucket
