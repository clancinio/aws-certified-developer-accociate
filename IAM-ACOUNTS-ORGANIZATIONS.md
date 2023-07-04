# IAM, ACCOUNTS, and AWS ORGANIZATIONS

## IAM Identity Policies

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

<br>

## IAM Users and ARNs

IAM Users are one of the identity types available inside AWS.

They are type you pick when you can identify a single individual or 'thing' which will use that identity - a person, an application or a service account.

![Blank diagram (2)](https://github.com/clancinio/aws-certified-developer-accociate/assets/20428737/06462967-ee62-4361-a60d-a2c1d1354358)
