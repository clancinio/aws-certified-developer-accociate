## CLOUD FORMATION

### Sample Template 

```yaml
Parameters:
  LatestAmiId:
    Type: 'AWS::SSM::Parameter::Value<AWS::EC2::Image::Id>'
    Default: '/aws/service/ami-amazon-linux-latest/al2023-ami-kernel-default-x86_64'
  SSHandWebLocation:
    Description: The IP address range that can be used to SSH to the EC2 instances
    Type: String
    MinLength: '9'
    MaxLength: '18'
    Default: 0.0.0.0/0
    AllowedPattern: '(\d{1,3})\.(\d{1,3})\.(\d{1,3})\.(\d{1,3})/(\d{1,2})'
    ConstraintDescription: must be a valid IP CIDR range of the form x.x.x.x/x. Default is 0.0.0.0/0 and is less safe.
Resources:
  EC2Instance:
    Type: AWS::EC2::Instance
    Properties:
      InstanceType: "t2.micro"
      ImageId: !Ref LatestAmiId
      IamInstanceProfile: !Ref SessionManagerInstanceProfile
      SecurityGroups:
        - !Ref InstanceSecurityGroup
  InstanceSecurityGroup:
    Type: 'AWS::EC2::SecurityGroup'
    Properties:
      GroupDescription: Enable SSH access via port 22 and 80
      SecurityGroupIngress:
        - IpProtocol: tcp
          FromPort: '22'
          ToPort: '22'
          CidrIp: !Ref SSHandWebLocation
        - IpProtocol: tcp
          FromPort: '80'
          ToPort: '80'
          CidrIp: !Ref SSHandWebLocation
  SessionManagerRole:
    Type: 'AWS::IAM::Role'
    Properties:
      AssumeRolePolicyDocument:
        Version: 2012-10-17
        Statement:
          - Effect: Allow
            Principal:
              Service:
              - ec2.amazonaws.com
            Action:
              - 'sts:AssumeRole'
      Path: /
      ManagedPolicyArns:
        - "arn:aws:iam::aws:policy/AmazonSSMManagedInstanceCore"
  SessionManagerInstanceProfile:
    Type: 'AWS::IAM::InstanceProfile'
    Properties:
      Path: /
      Roles:
        - !Ref SessionManagerRole
Outputs:
  InstanceId:
    Description: InstanceId of the newly created EC2 instance
    Value: !Ref EC2Instance
  AZ:
    Description: Availability Zone of the newly created EC2 instance
    Value: !GetAtt 
      - EC2Instance
      - AvailabilityZone
  PublicDNS:
    Description: Public DNSName of the newly created EC2 instance
    Value: !GetAtt 
      - EC2Instance
      - PublicDnsName
  PublicIP:
    Description: Public IP address of the newly created EC2 instance
    Value: !GetAtt 
      - EC2Instance
      - PublicIp 
```

This CloudFormation template defines the infrastructure for provisioning an EC2 instance with SSH and web access. Let's go through the important sections:

1. Parameters: This section allows you to pass input values to the template. In this case, there are two parameters defined:

2. LatestAmiId: Specifies the latest Amazon Machine Image (AMI) ID for the EC2 instance to use. It has a default value pointing to the latest Amazon Linux AMI.
SSHandWebLocation: Defines the IP address range that is allowed for SSH access. It has a default value of 0.0.0.0/0, allowing access from any IP address.
Resources: This section defines the AWS resources that will be created by the CloudFormation stack. The main resource is an EC2Instance of type "t2.micro" that uses the latest AMI specified by LatestAmiId. It also specifies the InstanceSecurityGroup, which controls inbound access to the EC2 instance.

3. EC2Instance: This resource defines the EC2 instance to be created. It specifies the instance type, the image ID retrieved from the LatestAmiId parameter, the IAM instance profile, and the security group.

4. InstanceSecurityGroup: This resource defines the security group associated with the EC2 instance. It allows inbound traffic on ports 22 (SSH) and 80 (HTTP) from the IP address range specified by the SSHandWebLocation parameter.

5. SessionManagerRole: This resource defines an IAM role that allows EC2 instances to assume the role. It specifies the role's trust policy, which allows the EC2 service to assume the role.

6. SessionManagerInstanceProfile: This resource creates an IAM instance profile that is associated with the EC2 instance. It includes the SessionManagerRole, allowing the instance to assume that role.

7. Outputs: This section defines the outputs of the CloudFormation stack. It provides information about the created EC2 instance, such as its InstanceId, Availability Zone (AZ), Public DNS name, and Public IP address.

Overall, this template creates an EC2 instance with the specified AMI, security group, and IAM role, allowing SSH and web access from the specified IP address range.
