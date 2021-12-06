deny -> allow -> allow
not explicit allow - default is implicit deny


Deny and allow has overlapping actions. Deny takes priority over allow but with condition.
```json
{
    "Version": "2012-10-17",
    "Statement": 
    [
      {
        "Effect":"Allow",
        "Action":[
           "s3:PutObject",
           "s3:PutObjectAcl",
           "s3:GetObject",
           "s3:GetObjectAcl",
           "s3:DeleteObject"
        ],
        "Resource":"arn:aws:s3:::holidaygifts/*"
      },
      {
        "Effect": "Deny",
        "Action": [
          "s3:GetObject",
          "s3:GetObjectAcl"
        ],
        "Resource":"arn:aws:s3:::holidaygifts/*",
        "Condition": {
            "DateGreaterThan": {"aws:CurrentTime": "2020-12-01T00:00:00Z"},
            "DateLessThan": {"aws:CurrentTime": "2020-12-25T06:00:00Z"}
        }
      }
    ]
}
```


Deny only with inverse action and inverse condition

- `DENY` does not apply for global services like (**iam, cloudfront, route53 and support**)
- `DENY` does apply for rest of the services if they are not in `eu-west-1` or `ap-southeast-2`

```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "DenyNonApprovedRegions",
            "Effect": "Deny",
            "NotAction": [
                "cloudfront:*",
                "iam:*",
                "route53:*",
                "support:*"
            ],
            "Resource": "*",
            "Condition": {
                "StringNotEquals": {
                    "aws:RequestedRegion": [
                        "ap-southeast-2",
                        "eu-west-1"
                    ]
                }
            }
        }
    ]
}
```

- allow list the buckets
- allow list the content of home and user dir
- only allow to do all operations for user dir

```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": [
                "s3:ListAllMyBuckets",
                "s3:GetBucketLocation"
            ],
            "Resource": "*"
        },
        {
            "Effect": "Allow",
            "Action": "s3:ListBucket",
            "Resource": "arn:aws:s3:::cl-animals4life",
            "Condition": {
                "StringLike": {
                    "s3:prefix": [
                        "",
                        "home/",
                        "home/${aws:username}/*"
                    ]
                }
            }
        },
        {
            "Effect": "Allow",
            "Action": "s3:*",
            "Resource": [
                "arn:aws:s3:::cl-animals4life/home/${aws:username}",
                "arn:aws:s3:::cl-animals4life/home/${aws:username}/*"
            ]
        }
    ]
}
```
 
