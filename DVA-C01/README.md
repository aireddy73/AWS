# AWS Certified Developer – Associate (DVA-C01) Notes
![AWS Certified Developer – Associate](images/DVA-C01.png)
## Table of contents

- AWS Fundamentals
    - [IAM: Identity Access & Management](1-aws-fundamentals/iam.md)
    - [EC2: Virtual Machines](1-aws-fundamentals/ec2.md)
    - [Security Groups](1-aws-fundamentals/security-groups.md)
    - [ELB: Elastic Load Balancers](1-aws-fundamentals/elb.md)
    - [ASG: Auto Scaling Group](1-aws-fundamentals/asg.md)
    - [EBS: Elastic Block Store](1-aws-fundamentals/ebs.md)
    - [EFS: Elastic File System](1-aws-fundamentals/efs.md)
    - [RDS: Relational Database Service](1-aws-fundamentals/rds.md)
    - [Route 53](1-aws-fundamentals/route53.md)
    - [ElastiCache](1-aws-fundamentals/elasticache.md)
    - [VPC: Virtual Private Cloud](1-aws-fundamentals/vpc.md)
    - [S3 Buckets](1-aws-fundamentals/s3.md)

- AWS Deep Dive
    - [Advanced S3](2-aws-deep-dive/advanced-s3.md)
    - [CLI: Command Line Interface](2-aws-deep-dive/cli.md)
    - [SDK: Software Development Kit](2-aws-deep-dive/sdk.md)
    - [Elastic Beanstalk](2-aws-deep-dive/elastic-beanstalk.md)
    - [Docker in AWS](2-aws-deep-dive/docker-in-aws/docker.md)
        - [Elastic Container Service](2-aws-deep-dive/docker-in-aws/ecs.md)
        - [Elastic Container Registry](2-aws-deep-dive/docker-in-aws/ecr.md)
        - [Fargate](2-aws-deep-dive/docker-in-aws/fargate.md)
    - [CICD: Continuous Integration and Deployment](2-aws-deep-dive/cicd/cicd.md)
        - [CodeCommit](2-aws-deep-dive/cicd/codecommit.md)
        - [CodePipeline](2-aws-deep-dive/cicd/codepipeline.md)
        - [CodeBuild](2-aws-deep-dive/cicd/codebuild.md)
        - [CodeDeploy](2-aws-deep-dive/cicd/codedeploy.md)
    - [CloudFormation](2-aws-deep-dive/cloudformation/cloudformation.md)
    - [CloudWatch](2-aws-deep-dive/monitoring-and-audit/cloudwatch.md)
    - [CloudFront](2-aws-deep-dive/cloudfront.md)
    - [Integration and Messaging](2-aws-deep-dive/integration-and-messaging/0-intro.md)
        - [SQS](2-aws-deep-dive/integration-and-messaging/1-sqs.md)
        - [SNS](2-aws-deep-dive/integration-and-messaging/2-sns.md)
        - [Kinesis](2-aws-deep-dive/integration-and-messaging/3-kinesis.md)

- [YAML](2-aws-deep-dive/yaml.md)

- [AWS Serverless](3-aws-serverless/serverless.md)
    - [Lambda](3-aws-serverless/lambda.md)
    - [DynamoDB](3-aws-serverless/dynamodb.md)
    - [API Gateway](3-aws-serverless/apigateway.md)
    - [SAM](3-aws-serverless/sam.md)
    - [Cognito](3-aws-serverless/cognito.md)
    - [Step Functions](3-aws-serverless/stepfunctions.md)
    - [AppSync](3-aws-serverless/appsync.md)

- Advanced Security
    - [STS: Security Token Service](4-aws-security/sts.md)
    - [Advanced IAM](4-aws-security/advanced-iam.md)
    - [Active Directories](4-aws-security/active-directories.md)
    - [Encryption](4-aws-security/encryption.md)
    - [KMS: Key Management Service](4-aws-security/kms.md)
    - [S3 Advanced Security](4-aws-security/s3-advanced-security.md)
    - [SSM Parameter Store](4-aws-security/ssm.md)
    - [Secrets Manager](4-aws-security/secrets-manager.md)
    - [CloudWatch Logs Encryption, CodeBuild Security](4-aws-security/other.md)

- Other Services
    - [AWS Certificate Manager](5-aws-other-services/acm.md)
    - [Databases Summary](5-aws-other-services/databases.md)
    - [Simple Email Service](5-aws-other-services/ses.md)

## Exam Preparation

- Exam details
    - Two question types:
        - Multiple Choice
        - Multiple response
    - Minimum passing score: 720/1000
    - Domains:
        - Deployment: CICD, Beanstalk, Serverless
        - Security: each service deep-dive + dedicated section
        - Development with AWS Services: Serverless, API, SDK, & CLI
        - Refactoring: Understand all the AWS services for the best migration
        - Monitoring and Troubleshooting: CloudWAtch, CloudTrail, X-Ray
    - Exam Guide: [Certified Developer - Associate Exam PDF](https://d1.awsstatic.com/training-and-certification/docs-dev-associate/AWS_Certified_Developer_Associate-Exam_Guide_EN_1.4.pdf)

- EC2 + IAM Exam Checklist
    - Know how to SSH into EC2 (and change .pem file permissions) 
    - Know how to properly use security groups 
    - Know the fundamental differences between private vs public vs elastic IP 
    - Know how to use User Data to customize your instance at boot time 
    - Know that you can build custom AMI to enhance your OS 
    - EC2 instances are billed by the second and can be easily created and thrown away, welcome to the cloud! 
- Maybe on Exam:
    - Availability zones are in geographically isolated data centers
    - IAM users are NOT defined on a per-region basis
    - If you are getting a permission error exception when trying to SSH into your linux instance, then the key is missing chmod 400 permissions
    - If you are getting a network timeout when trying to SSH into your EC2 instance, then your security groups are misconfigured
    - Security groups reference IP address, CIDR block, Security group, but NOT DNS name

# Credits

- These notes are based on the [Ultimate AWS Certified Developer Associate 2021](https://www.udemy.com/course/aws-certified-developer-associate-dva-c01/) course by Stephane Maarek

## My other AWS Certification Notes
- [AWS Certified Developer – Associate (DVA-C01)](https://github.com/aireddy73/AWS/tree/main/DVA-C01)
- [AWS Certified Solutions Architect – Associate (SAA-C02)](https://github.com/aireddy73/AWS/tree/main/SAA-C02)
- [AWS SysOps Administrator Associate SOA-C02](https://github.com/aireddy73/AWS/tree/main/SOA-C02)
- [AWS Certified DevOps Engineer – Professional (DOP-C01)](https://github.com/aireddy73/AWS/tree/main/DOP-C01)
- [AWS Certified Solutions Architect – Professional (SAP-C01)](https://github.com/aireddy73/AWS/tree/main/SAP-C01)
