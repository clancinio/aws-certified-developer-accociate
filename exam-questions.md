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
- Account wide Auditing and API Logging :white_check_mark:

### 8. Is it possible to restrict what the Account Root User can do?

- Always
- Never
- If AWS Organisations are used
- If AWS Organizations are used (but not the management account) :white_check_mark:


### 9. What is Role Switching?

- Changing the permissions on an IAM Role
- Changing the TRUST on a Role
- Changing who can assume a Role
- Logging into a Role
- Assuming a role in another AWS account to access that account via the console UI :white_check_mark:


### 10. What is Role Switching?What are valid IAM Policy types?

- AWS Managed Policy :white_check_mark:
- Customer Managed Policy :white_check_mark:
- Self-Managed Policy
- Inline Policies :white_check_mark:
- External Policies

<br>
<hr>

## CloudWatch

### 1. Your company manages hundreds of EC2 instances running on Linux OS. The instances are configured in several Availability Zones in the eu-west-3 region. Your manager has requested to collect system memory metrics on all EC2 instances using a script.

### Which of the following solutions will help you collect this data?

- Use a cron job on the instances that pushes the EC2 RAM statistics as a Custom metric into CloudWatch :white_check_mark:
- Extract RAM statistics using the instance metadata"
- Extract RAM statistics from the standard CloudWatch metrics for EC2 instances"
- Extract RAM statistics using X-Ray

The Amazon CloudWatch Monitoring Scripts for Amazon Elastic Compute Cloud (Amazon EC2) Linux-based instances demonstrate how to produce and consume Amazon CloudWatch custom metrics. These Perl scripts comprise a fully functional example that reports memory, swap, and disk space utilization metrics for a Linux instance. You can set a cron schedule for metrics reported to CloudWatch and report memory utilization to CloudWatch every x minutes.

<br>

### 2. An IT company uses a blue/green deployment policy to provision new Amazon EC2 instances in an Auto Scaling group behind a new Application Load Balancer for each new application version. The current set up requires the users to log in after every new deployment.

### As a Developer Associate, what advice would you give to the company for resolving this issue?

- Use rolling updates instead of a blue/green deployment
- Use ElastiCache to maintain user sessions :white_check_mark:
- Enable sticky sessions in the Application Load Balancer
- Use multicast to replicate session information

Amazon ElastiCache allows you to seamlessly set up, run, and scale popular open-Source compatible in-memory data stores in the cloud. Build data-intensive apps or boost the performance of your existing databases by retrieving data from high throughput and low latency in-memory data stores. Amazon ElastiCache is a popular choice for real-time use cases like Caching, Session Stores, Gaming, Geospatial Services, Real-Time Analytics, and Queuing.

To address scalability and to provide a shared data storage for sessions that can be accessed from any individual web server, you can abstract the HTTP sessions from the web servers themselves. A common solution to for this is to leverage an In-Memory Key/Value store such as Redis and Memcached via ElastiCache.

<br>

### 3. Your company manages MySQL databases on EC2 instances to have full control. Applications on other EC2 instances managed by an ASG make requests to these databases to get information that displays data on dashboards viewed on mobile phones, tablets, and web browsers.

### Your manager would like to scale your Auto Scaling group based on the number of requests per minute. How can you achieve this?

- Attach an Elastic Load Balancer
- You create a CloudWatch custom metric and build an alarm to scale your ASG :white_check_mark:
- Attach additional Elastic File Storage
- You enable detailed monitoring and use that to scale your ASG 

<br>

### 4. A cybersecurity company is publishing critical log data to a log group in Amazon CloudWatch Logs, which was created 3 months ago. The company must encrypt the log data using an AWS KMS customer master key (CMK), so any future data can be encrypted to meet the company’s security guidelines.

### How can the company address this use-case?

- Use the AWS CLI `create-log-group` command and specify the KMS key ARN
- Use the AWS CLI `describe-log-groups` command and specify the KMS key ARN
- Use the AWS CLI `associate-kms-key` command and specify the KMS key ARN :white_check_mark:
- Enable the encrypt feature on the log group via the CloudWatch Logs console 

<br>
<hr>

## S3

### 1. A development team had enabled and configured CloudTrail for all the Amazon S3 buckets used in a project. The project manager owns all the S3 buckets used in the project. However, the manager noticed that he did not receive any object-level API access logs when the data was read by another AWS account.

### What could be the reason for this behavior/error?

- CloudTrail always delivers object-level API access logs to the requester and not to object owner
- CloudTrail needs to be configured on both the AWS accounts for receiving the access logs in cross-account access
- The bucket owner also needs to be object owner to get the object access logs :white_check_mark:
- The meta-data of the bucket is in an invalid state and needs to be corrected by the bucket owner from AWS console to fix the issue

<br>

### 2. A Developer has been entrusted with the job of securing certain S3 buckets that are shared by a large team of users. Last time, a bucket policy was changed, the bucket was erroneously available for everyone, outside the organization too.

### Which feature/service will help the developer identify similar security issues with minimum effort?

- S£ Analytics
- S3 Object Lock
- Access Advisor feature on IAM Console
- IAM Access Analyzer :white_check_mark:


<br>
<hr>

## Cloud Formation
### 1. You are creating a Cloud Formation template to deploy your CMS application running on an EC2 instance within your AWS account. Since the application will be deployed across multiple regions, you need to create a map of all the possible values for the base AMI.

### How will you invoke the !FindInMap function to fulfill this use case?

- !FindInMap [ MapName, TopLevelKey ]

- !FindInMap [ MapName, TopLevelKey, SecondLevelKey]  :white_check_mark:

- !FindInMap [ MapName ]

- !FindInMap [ MapName, TopLevelKey, SecondLevelKey, ThirdLevelKey ]