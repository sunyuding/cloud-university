# AWS
- (Tutorial) Amazon AWS - https://aws.amazon.com/getting-started/tutorials/

How does AWS define cloud computing?
- The on-demand delivery of IT resources through a cloud services platform via the Internet with pay-as-you-go pricing.

Which of the following examples best demonstrates the agility that cloud computing offers?
- Spin up servers in minutes, and shut down servers when you don't need them.

## Learning Paths
- https://aws.amazon.com/training/learning-paths

- [A curated list of AWS resources to prepare for the AWS Certifications](https://gist.github.com/leonardofed/bbf6459ad154ad5215d354f3825435dc)
- [AWS Cert Quiz Show](https://www.aws.training/LearningLibrary?&search=CQ&tab=digital_courses)

### AWS Certified Cloud Practitioner
- https://aws.amazon.com/training/path-cloudpractitioner/
- [AWS Certified Cloud Practitioner
(CLF-C01) Exam Guide](https://d1.awsstatic.com/training-and-certification/Docs%20-%20Cloud%20Practitioner/AWS_Certified_Cloud_Practitioner-Exam_Guide_EN_v1.6.pdf)
- [AWS Cloud Practitioner Essentials (Second Edition)](https://aws.amazon.com/training/course-descriptions/cloud-practitioner-essentials/)
- [Flashcards](https://quizlet.com/275297341/amazon-cloud-practitioner-certification-flash-cards/)

### AWS Certified Architect
- https://aws.amazon.com/training/path-architecting/
- [ ] [AWS Certified Solution Architect - Associate 2019 Exam Notes](https://github.com/AlessioCasco/AWS-CSA-2019-study-notes)
- [https://cliffordandrewboyd.com/wordpress/wp-content/uploads/2018/10/eBook.pdf](https://cliffordandrewboyd.com/wordpress/wp-content/uploads/2018/10/eBook.pdf)
- [AWS Certified Solutions Architect Associate Exam Blueprint](https://d0.awsstatic.com/training-and-certification/docs-sa-assoc/AWS_certified_solutions_architect_associate_blueprint.pdf)


Three ways to use AWS
1. AWS Management Console
2. Command Line Interface (CLI)
3. Software Development Kits (SDKs)

Which of the following terms refers to the power of scale computing resources up or down easily?
- Elasticity

## Computing
### [Amazon Elastic Cloud Compute (EC2)](ec2.md)

### ECR
Amazon Elastic Container Registry (ECR) is a fully-managed Docker container registry that makes it easy for developers to store, manage, and deploy Docker container images.

```
aws ecr get-login --region us-west-2 --no-include-email --profile=engineering
```

[Using the AWS CLI with Amazon ECR](https://docs.aws.amazon.com/AmazonECR/latest/userguide/ECR_AWSCLI.html)

### [Amazon Elastic Kubernetes Service (EKS)](eks.md)

## Storage
### [Amazon Simple Storage Service (S3)](s3.md)

### [Amazon Elastic Block Store (EBS)](ebs.md)

### Storage Gateway
Three different types of gateways 
– [Tape Gateway](https://aws.amazon.com/storagegateway/vtl/) 
- [File Gateway](https://aws.amazon.com/storagegateway/file/)
- [Volume Gateway](https://aws.amazon.com/storagegateway/volume/)

Q. Your company needs to store 200TB of oproduct videos. The videos were created over the last several years, with the most recent being accessed the most often. The data must be accessed locally, but there is insufficient space in the data center to install sufficient local sotrage devices to store this data. What service will meet these requirements? 
- [AWS Storage Gateway - Cached volumes]

### Amazon Glacier Storage


## AWS Regions
Your company has deployed resources across several AWS regions. Your CTO has mandated that developers and operations can only use N.Virginia, Frankfurt and Mumbai as regions. She is particularly concerned with ensuring that any solution scales when AWS releases new regions. What should you do?
- Use a SCP at the root of the organization to block assignment of permissions to anything except the three regions. 

## Networking
What statement is true about Internet gateways?
- An Internet gateway is needed if you want to connect to AWS services outside of the VPC.

### [Amazon Virtual Private Cloud (VPC)](vpc.md)

### Security Groups
Act as built-in **firewalls**. 

An Amazon VPC security group can be associated with:
- An Elastic Network Interface

### AWS VPN
- AWS Site-to-Site VPN
    - Static
    - Dynamic
- AWS Client VPN

Q. How would you configure a VPC to accept VPN connections so that many users could connect usng an OpenVPN-based client?
- Create an [AWS Client VPN Endpoint](https://docs.aws.amazon.com/vpn/latest/clientvpn-admin/cvpn-working-endpoints.html) and attach it to a VPC subnet

### [Elastic Load Balancer](elb.md) 

### Elastic IP Address

### Auto Scaling
Create resources on demand.
1. How can I ensure that my workload has enough EC2 resources to meet fluctuating performance requirements? - Scalability
2. How can I automate EC2 resource provisioning to occur on-demand? - Automation

- Scale out - launch instance
- Scale in - terminate instance

Launch Configuration => Auto Scaling Group => Auto Scaling Policy

No additional charge

What does the phrase '**stop guessing capacity**' mean?
- Use of **auto scaling** to prevent the need to predict and guess your capacity and demand requirement

What are characteristics of the Amazon EC2 Auto Scaling service?
- Responds to changing condifions by Terminating and Launching Amazon EC2 instances
- Enforces a minimum number of running Amazon EC2 instances

### [Amazon Route 53](route53.md)

### [AWS Direct Connect](direct-connect.md)

### Amazon Relational Database Services (RDS)
- MySQL
- Amazon Aurora
- SQL Server
- PostgreSQL
- MariaDB
- Oracle

No charge for backup storage of up to 100% of database storage

750 instance-hours of RDS is available in the free-tier in the 1st year as well as 20GB of SSD general purpose storage and 20 GB of backup storage free per month.

What does Amazon manage on my behalf for RDS?
- Provisioning Infrastructure Capacity, Installing Software, replication of db across multiple AZ's (multi-AZ deployment), backups, patching software, and failovers are managed on behalf of RDS users.

It takes away the time consuming tasks of hardware provisioning, setup, patching, and backups so you can focus on your applications.

When using Amazon RDS Multi-AZ, how can you offload read requests from the primary?
- Add a read replica DB instance, and configure the client's application logic to use a read-replica.
- Use [ElastiCache](https://aws.amazon.com/elasticache/) to cache frequently used data. Update the application logic to read/write from the cache.

Q. If there are multiple Read Replicas for a primary Amazon RDS DB instance and one of them is promoted, what happens to the rest of the Read Replicas?
- There is no change in their behavior

Q. Your team is building an order processing system that will span multiple Availability Zones. During testing, the team wants to test how the application will react to a database failover. How can you enable this type of test?
- Reboot the primary instance from the Amazon RDS console.

### Amazon DynamoDB
Q. Which Amazon DynamoDB operation will you use to retrieve the metadata attributes from the table?
- Query operation

### AWS Lambda
Fulling managed serverless.

Q. You have configured an AWS Lambda function to launch an Amazon EC2 Linux instance each Sunday night to run a 30-minute batch job.

What would be the most reliable way to terminate the instance after it has completed the batch job?
- [x] Have the instance run "sudo shutdown now -h"
- Create an AWS Batch job configured to run once per week to terminate the instance with a known Tag

### AWS Elastic Beanstalk
- Platform as a Service(PaaS)
- Out-of-the-box load balancing and autoscaling
- Can still access underlying AWS resources with full control

Create application => Upload version => Launch environment => Manage

What is the first step in getting started with AWS Lambda?
- Upload your code

### [Amazon Simple Queue Service (SQS)](sqs.md)

### Amazon Simple Notification Service (SNS)
Flexible, fully managed **pub/sub messaging** and mobile communications service.

Q. What is an efficient way to fan-out a single Amazon SNS message to multiple Amazon SQS queues?
- Create multiple SQS queues that subscribe to the SNS topic.

Q. When can an Amazon SNS message be deleted after being published to a topic?
- Messages cannot be deleted

### Amazon CloudFront
CDN. Speeds up the delivery of your content to viewers across the globe.

Q. Your company provides media content via the Internet to customers through a paid subscription model. You leverage **Amazon CloudFront** to distribute content from an Amazon S3 bucket. What approach can you use to serve this private content securely to your paid subscribers?
1. [x] Provide signed CloudFront URLs to authenticated users.
2. Add subscriber IP addresses to the CloudFront security group.
3. Use the geo restriction feature to restrict access to all of the paid subscription media at the country level.
4. Provide subscribers with an **Origin Access Identity** to grant them access to the CloudFront distribution.

Q. What does Amazon CloudFront do when it uses HTTP Live Streaming(HLS), HTTP Dynamic Streaming (HDS), Smooth Streaming, and MPEG DASH formats for streaming video?
- Encapsulates video into pull (rather than push) formats that allow clients to adapt to changing conditions for improved performance

## CodeCommit
### Setup permissions
https://youtu.be/W-SM4m19JMA

## AWS Cloud9

## AWS Trusted Advisor
Trusted Advisor provides best practices (or checks) in four categories:
- Cost Optimization
- Performance
- Security
- Fault Tolerance

Which of the following statements best describes AWS Trusted Advisor?
- A tool that provides you real time guidance to help you provision your resources following AWS best practices.

## AWS Transfer for SFTP
AWS Transfer for SFTP is a fully managed service that enables the transfer of files directly into and out of Amazon S3 using the Secure File Transfer Protocol (SFTP)—also known as Secure Shell (SSH) File Transfer Protocol. 

## Security, Identity, & Compliance
### [Identity and Access Management (IAM)](iam.md)

### Amazon Cognito
Which of the following statements best describes **Amazon Cognito**?
- It is a simple user-data synchronization and identity service that helps you securely manage and synchronize app data for your users across their mobile devices.

### Key Management Service (KMS)
How is Key Management Service (KMS) priced?
- KMS is priced per customer master key and the number of requests received per month. _Explanation: KMS is priced per two factors: the number of Customer Master Keys maintained in
KMS and the number of requests received within a month._

Q. Your company as a policy of rotating Access Keys each quarter. How can you rotate Access Keys with minimal impact on your applications?
- Create an additional Access Key. Update the applications with the new Access Key, then delete the old Access Key.

Q. Which of the following is true when using AWS Key Management Service(AWS KMS)?
- Use of keys is protected by access control policies defined and managed by you.

### AWS Shield
**AWS Shield** is a managed **Distributed Denial of Service (DDoS)** protection service that safeguards applications running on AWS.
- AWS Shield Standard
    - Automatic protection
- AWS Shield Advanced
    - Specialized support

### AWS Config
Which statement is true about AWS Config and Regions?
- AWS Config is a Region specific service, meaning it has to be configured in every region you wish to use it

### AWS Directory Service
https://aws.amazon.com/directoryservice/

## CloudTrail
Which other AWS service can you use to enable greater security of your CloudTrail log files?
- Key Management Service (KMS)
_The use of AWS KMS is an optional element of CloudTrail, but it allows additional
encryption to be added to your Log files when stored on S3_

The AWS CloudTrail service provides which of the following?
- Logs of the API requests for AWS resources within your account

Q. A third-party security application is making API calls to your AWS account. However, it is failing to operate correctly and returns a generic "Access Denied" message. Where can you look to identity the cause of this error?
- AWS CloudTrail

## Edge Locations

## Amazon Kinesis Data Firehose
What service will enable you to ingest this this stream of data and store it to Amazon S3 for future processing?
- **Amazon Kinesis Data Firehose**

## Continuous Integration, Delivery, and Deployment
### AWS CodeBuild
continuous integration

### AWS CodeDeploy
continuous deployment

### AWS CodePipeline
full code pipeline from build to deploy

### AWS CodeStart
integrates all parts of the process with project management tools and JIRA issue tracking

## Infrastructure as Code
### AWS CloudFormation
Automate AWS resources provisioning.

### OpsWorks
IaC with Chef

## Serverless/FaaS
### AWS Lambda
run serverless functions on AWS

Q. Your "www.example.com" domain is pointing to an Amazon EC2 instance. How could you keep this operating, but send requests for "www.example.com/news/" to an AWS Lambda function?
- Use an **Application Load Balancer** with a separate **Target Group**

## Monitoring
### [Amazon CloudWatch](cloudwatch.md)

## AWS Cloud Development Kit (AWS CDK)
- [ ] [Infrastructure is Code with the AWS CDK - AWS Online Tech Talks](https://www.youtube.com/watch?v=ZWCvNFUN-sU)

A multi-language software developement framework fro modeling cloud infrastructure as reusable components.

- Core Framework
- AWS Construct Library
- AWS CDK CLI

https://docs.aws.amazon.com/cdk/latest/guide/getting_started.html

## AWS Well-Architected Framework
- https://aws.amazon.com/architecture/well-architected/
- https://d1.awsstatic.com/whitepapers/architecture/AWS_Well-Architected_Framework.pdf
- The Five Pillars of the Framework
    - Security
        - Identity and access management (IAM)
        - Detective controls
        - Implement security at all layers
        - Enable **traceability**
        - Apply **principle of least privilege**
    - Reliability
        - Recover from issues/failures
        - Automatically recover
        - Scale horizontally
    - Performance Efficiency
        - Monitor AWS services
    - Cost Optimization
        - Use cose-effective resources
    - Operational Excellence
        - Manage and automate changes

Which of the pillars of the Well-Architected Framework is defined as the ability to run and monitor systems to deliver business value and to continually improve supporting processes and procedures?
- Operational excellence

Why does AWS recommend using stateless cloud applications, when possible?
- Decoupling layers enables more scalability and resilience

Question: Your company wants to host its secure web application in AWS. The internal security policies consider any connections to or from the web server as insecure and require application data protection. What approaches should you use to protect data in transit for the application? (Choose 2 answers)
- A. Use BitLocker to encrypt data.
- B. Use HTTPS with server certificate authentication.
- C. Use an AWS Identity and Access Management (IAM) role.
- D. Use Secure Sockets Layer (SSL)/Transport Layer Security (TLS) for database connection.
- E. Use XML for data transfer from client to server.

Answer: B and D. To protect data in transit from the clients to the web application, HTTPS with server certificate authentication should be used. To protect data in transit from the web application to the database, SSL/TLS for database connection should be used.

## The Shared Responsibility Model
|              |
|--------------|
|User Data     |
|Application   |
|Guest OS      |
|--------------|
|Hypervisor    |
|Network       |
|Physical      |

## Security Compliance
Components of AWS compliance
- Risk management
- Control environment
- Information security

Your customers are concerned about the security of their sensitive data and their inquiry asks
about what happens to old storage devices on AWS. What would be the best answer to this question? 
- AWS uses the techniques detailed in DoD 5220.22-M to destroy data as part of the decommissioning process. 
_Explanation: When a storage device has reached the end of its useful life, AWS procedures
include a decommissioning process that is designed to prevent customer data from being
exposed to unauthorized individuals.
AWS uses the techniques detailed in DoD 5220.22-M (“National Industrial Security Program
Operating Manual “) or NIST 800-88 (“Guidelines for Media Sanitization”) to destroy data as part
of the decommissioning process.
All decommissioned magnetic storage devices are degaussed and physically destroyed in
accordance with industry-standard practices.
Reference: https://d0.awsstatic.com/whitepapers/aws-security-whitepaper.pdf_

## Pricing
- Pay as you go
- Pay less when you reserve
- Pay even less per unit by using more
- Pay even less as AWS grows

Pay for:
- Compute capacity
- Storage
- Outbound data transfer (aggregated)

There are no outbound data trasfer charges between Amazon Web Services in the same Region 

No charge for:
- **in-bound data transfer** across all AWS services in all regions

## AWS Budgets
Three budget types are available - **cost**, **usage**, and **reserved instance utilization**.
**Data transfer** is not a specific budget type, but the cost related to data transfers would be monitored under the cost budgets.

## AWS Support Plans
**AWS Support** offers four support plans:
- Basic Support
- Developer Support
- Business Support
- Enterprise Support
    - **Technical Account Manager** 
    - Support Concierge
    - designated senior customer service professional
    - Well-Architected Review by AWS Solution Architects

Which AWS Support plans include the use of a **Health API** that can be used in support applications to get the status and health of your AWS resources?
Which AWS Support plans include access to the full set of **Trusted Advisor Checks** and guidance?
- Business and Enterprise Support Plans

How can you obtain a report that shows your current monthly spending with AWS and an estimate of how much you will be spending this entire month?
- Use the **My Billing Dashboard** to see your current spend and what your estimated total monthly spend would be.

## AWS Command Line Interface
```bash
$ aws configure --profile produser
AWS Access Key ID [None]: AKIAI44QH8DHBEXAMPLE
AWS Secret Access Key [None]: je7MtGbClwBF/2Zp9Utk/h3yCo8nvbEXAMPLEKEY
Default region name [None]: us-east-1
Default output format [None]: text
```

## Reference
- [ ] [A Beginner's Guide To Scaling To 11 Million+ Users On Amazon's AWS](http://highscalability.com/blog/2016/1/11/a-beginners-guide-to-scaling-to-11-million-users-on-amazons.html)

- [ ] [2007: Dynamo: Amazon’s Highly Available Key-value Store](http://s3.amazonaws.com/AllThingsDistributed/sosp/amazon-dynamo-sosp2007.pdf)
- [Free Digital Training](https://www.aws.training/LearningLibrary?&search=&tab=digital_courses)