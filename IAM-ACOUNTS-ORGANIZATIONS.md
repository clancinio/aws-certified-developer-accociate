# IAM, ACCOUNTS, and AWS ORGANIZATIONS

<hr>

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
<hr>


## IAM Users and ARNs

### IAM Users

IAM Users are one of the identity types available inside AWS.

They are type you pick when you can identify a single individual or 'thing' which will use that identity - a person, an application or a service account.

![Blank diagram (2)](https://github.com/clancinio/aws-certified-developer-accociate/assets/20428737/06462967-ee62-4361-a60d-a2c1d1354358)

### ARNs

Amazon Resource Name (ARN)

- Uniquely identify resources within any AWS accounts.

```
arn:partition:service:region:account-id:resource-id
arn:partition:service:region:account-id:resource-type/resource:id
arn:partition:service:region:account-id:resource-type:resource:id

arn:aws:s3:::doggifs        // Buckets
arn:aws:s3:::doggifs/*      // Objects in the bucket
```

### Exam Tips  

- _5,000 IAM Users per account_ *
- IAM Users can be a member of 10 groups 
- This has systems design impacts...
- Internet-scale application
- Large orgs & org merges
- IAM Roles & Identity Federation fix this (more on this later)

<br>
<hr>

## IAM Groups

IAM Groups are containers for Users

- Groups can have Policies attached to them (Inline and Managed)

![](images/Blank_diagram(3).png)

<br>
<hr>

## IAM Roles

### When to use IAM Roles

**Web Identities**  

Advantages of Roles in this situation:

- No AWS Credentials on the app
- Uses Existing customers logins 
- Scales to 1000,000,000's of accounts

![](images/Roles_Web_Identies.png)

<br>

**Cross Account Access**  

- Use role in partner accounts
- Your users can assume that role, and get temporary user credentials, and use those to upload objects.
- Because the IAM Role in the partner account is an identity in that account, then using that role means that any objects that you upload to that bucket are owned by the partner account.

![](images/Multi_Account.png)

<br>
<hr>

## Security Token Service (STS)

- Generates temporary credentials (sts:AssumeRole*)
- They expire and don't belong to the identity
- Limited access
- Used to access AWS resources
- Requested by an identity (AWS or EXTERNAL)

![](images/sts.png)

<br>
<hr>

## AWS Organizations 

AWS Organizations is a product which allows larger businesses to manage multiple AWS accounts in a cost-effective way.

Without AWS organizations, a business with multiple AWS accounts would need to have its own pool of IAM Users for each account, and separate payment methods:

![](images/orgs1.png)


With a standard AWS account (AWS account that is not in an organization), you create an AWS Organization.

- The organization isn't in the AWS account, you just use the account to create the Organization
- This account that you used to create the Organization becomes the _**Management Account**_
- Using this management account, you can invite other existing standard AWS account into the organization
- These account will need to approve the invite to join the org. These account will become part of the organization.
- When these account join the organization, then change from **_standard accounts_** to _**member accounts**_ of that organization 

![](images/orgs2.png)

- You can also create new accounts directly withing the organization (Just need unique email)
- Adding accounts in this way means there is no invite process
- With orgs, you don't need to have IAM User inside every AWS account. Instead, AWS Roles can be used to allow IAM User to access other AWS accounts

<br>
<hr>

## Service Control Policies (SCP)

- SCPs are **_account permissions boundaries_**
- The management account is the only account within an AWS Organization that can't be restricted using SCPs
- They limit what the account (including root user) can do
- With a SCP, you actually restrict what an account itself can do. Restricting the account, in effect, restricts the root user.
- _SCPs don't actually grant any access rights, they establish which permission can be granted in an account_***

![](images/SPC.png)

The concept of a SCP:
- JSON Document
- The policies can be attached to the Root Container of the Organization (Organization as a whole), one or more OU's, and indicidual AWS accounts
- SCP inherit down the organizational tree.

