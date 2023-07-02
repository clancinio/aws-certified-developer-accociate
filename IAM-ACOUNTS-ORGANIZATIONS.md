## IAM, ACCOUNTS, and AWS ORGANIZATIONS

### IAM Identity Policies

An identity policy in AWS IAM determines the permissions and access rights for users or groups. It specifies the actions and resources they can access in AWS. Identity policies ensure secure and controlled access to AWS services, following the principle of least privilege.

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "s3:GetObject",
        "s3:PutObject",
        "dynamodb:GetItem",
        "dynamodb:PutItem",
        "dynamodb:DeleteItem"
      ],
      "Resource": [
        "arn:aws:s3:::example-bucket/*",
        "arn:aws:dynamodb:us-east-1:123456789012:table/example-table"
      ]
    }
  ]
}
```

This single statement allows the following actions on resources:

- `s3:GetObject` and `s3:PutObject` on objects within the "example-bucket" S3 bucket.
- `dynamodb:GetItem`, `dynamodb:PutItem`, and `dynamodb:DeleteItem` on the "example-table" DynamoDB table in the US East (N. Virginia) region.

### Handle Overlap in Access

- Explicit Deny - Overrules everthing else
- Explicit Alow - Take effect unless there is an explicit Deny (Deny always wins)
- Default Deny (Implicit)


### IAM Users and ARNs
