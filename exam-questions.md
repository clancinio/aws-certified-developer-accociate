# Practice Exam Questions

<hr>

## AWS Fundamentals


### 1. What permissions options does an AMI have?

- Public Access, Owner only, Specific AWS Accounts :white_check_mark:
- Public Access, Owner only, Specific IAM Users
- Public Access, Owner only, Specific Regions 
- Public Access, Specific AWS Accounts, Specific IAM Users 

### 2. EC2 is an example of which service model?

- PAAS
- IAAS :white_check_mark:
- SAAS
- DBaaS
- FaaS


### 3. What is true of an AWS Public Service?

- Located in the public internet zone
- Located in the AWS Public zone :white_check_mark:
- Located in a VPC
- Publicly accessible by anyone
- Anyone can connect, but permissions are required to access the service :white_check_mark:

### 4. What is true of an AWS Private Service

- Located on the Public Internet
- Located in the AWS Public Zone
- Located in a VPC :white_check_mark:
- Accessible from the VPC it is located in :white_check_mark:
- Accessible from any other VPC
- Accessible from other VPCs or on-premises networks as long as private networking is configured :white_check_mark:

### 5. What is true of Simple Storage Service (S3)

- S3 is an AWS Public Service :white_check_mark:
- S3 is a private service
- S3 is an web scale block storage system
- S3 is a object storage system :white_check_mark:
- Buckets can store a limit of 100TB of data
- Buckets can store an unlimited amount of data :white_check_mark:

### 6. What is a CloudFormation Logical Resource

- A resource in a stack which hasn't been created yet 
- A resource defined in a CloudFormation Template :white_check_mark:
- A resource created in an AWS Account by CloudFormation
- A name given to a resource created with best practice configuration

### 7. What is a CloudFormation Physical resource

- A resource defined in a CloudFormation template i.e EC2Instance
- A physical resource created by creating a CloudFormation stack :white_check_mark:
- A product in AWS which is a physical piece of hardware i.e a router
- None of the above

### 8. What is a simple and correct definition of High Availability?

- A system which maximises uptime :white_check_mark:
- A System which is highly performing
- A System which can operate through failure
- A System which has regular backups and restore processes

### 9. Which of the following is a correct definition of a fault tolerant system?

- A system which uses automation to return a service to operational status with little user disruption
- A system which has a 99.999% uptime
- A system which allows failure, and can continue operating without disruption :white_check_mark:
- A system which has regular and reliable system backups and restore processes

### 10. How many DNS root servers exist?

- 12
- 13 :white_check_mark:
- 7
- 100

### 11. Who manages the DNS Root Servers?

- IANA
- 12 Large Organisations :white_check_mark:
- IANA Root Server board
- Google

### 12.Who Manages the DNS Root Zone

- IANA :white_check_mark:
- 12 Large Organisations
- IANA Root Server Board
- Microsoft
- Nobody manages the root zone - its managed via the root hints file

### 13. Which DNS Record Type converts a HOST into an IPv4 Address

- A :white_check_mark:
- AAAA
- TXT
- MX
- CNAME
- NS

### 14. Which DNS Record type is how the root zone delegates control of .org to the .org registry

- A
- AAAA
- TXT
- CNAME
- MX
- NS :white_check_mark:

### 15. Which type of organisation maintains the zones for a TLD (e.g .ORG)

- Registrar
- Registry :white_check_mark:
- IANA
- None of the above

### 16. Which type of organisation has relationships with the .org TLD zone manager allowing domain registration?

- Registrar :white_check_mark:
- Registry
- IANA
- None of the above

### 17. How many subnets are in a default VPC

- 2
- 3
- Equal to the number of AZs in the region the VPC is located in :white_check_mark:
- 10

### 18. What is the IP CIDR of a default VPC

- It depends on the region
- Random based on the AWS account
- You can configure an IP range suitable for your network
- 172.31.0.0/16  :white_check_mark:
- 10.0.0.0/16

<br>
<hr>

## IAM, ACCOUNTS AND AWS ORGANISATIONS

### 1. Is there a limit to the number of IAM users in an AWS Account? if so, how many? 

- No Limit
- 1,000 per region
- 3,000 per account
- 5,000 per account :white_check_mark:
- 5,000 per region

### 2. Which of the following are features of IAM groups?

- Admin groupings of IAM Users :white_check_mark:
- Can hold Identity Permissions :white_check_mark:
- Can be used to login (Access Keys)
- Can be used to login (Username and password)
- Can be nested

### 3. Within AWS policies, what is always a priority?

- Explicit Allow
- Explicit Deny  :white_check_mark:
- Depends on the order in the policy
- No priority

### 4. What two policies are assigned to an IAM Role

- Permissions Policy :white_check_mark:
- Assumption Policy
- Resource Policy
- Trust Policy :white_check_mark:

### 5. Which of the following are true for IAM Roles

- Roles have associated Long Term Credentials (Access Keys)
- Roles can be assumed :white_check_mark:
- When assumed - temporary credentials are generated :white_check_mark:
- Roles can be logged into
- When an identity logs into a role - temporary credentials are generated

### 6. What Three features are provided by AWS Organizations (pick all that apply)

- Consolidated billing  :white_check_mark:
- Managed assistance for company and AWS account mergers
- AWS Account restrictions using SCP  :white_check_mark:
- Account organisation via OU's  :white_check_mark:
- Protection against credential leaks
- Company ID reports

### 7. What functionality is provided by CloudTrail

- Log Ingestion
- Metrics management
- Account Restrictions
- Account wide Auditing and API Logging

