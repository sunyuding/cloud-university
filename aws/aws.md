# AWS
- (Tutorial) Amazon AWS - https://aws.amazon.com/getting-started/tutorials/

How does AWS define cloud computing?
- The on-demand delivery of IT resources through a cloud services platform via the Internet with pay-as-you-go pricing.

Which of the following examples best demonstrates the agility that cloud computing offers?
- Spin up servers in minutes, and shut down servers when you don't need them.

## Learning Paths
- https://aws.amazon.com/training/learning-paths

- [A curated list of AWS resources to prepare for the AWS Certifications](https://gist.github.com/leonardofed/bbf6459ad154ad5215d354f3825435dc)

- [CQ: The AWS Certification Quiz Show](https://www.aws.training/LearningLibrary?&search=CQ&tab=digital_courses)

### AWS Certified Cloud Practitioner
- https://aws.amazon.com/training/path-cloudpractitioner/
- [AWS Certified Cloud Practitioner
(CLF-C01) Exam Guide](https://d1.awsstatic.com/training-and-certification/Docs%20-%20Cloud%20Practitioner/AWS_Certified_Cloud_Practitioner-Exam_Guide_EN_v1.6.pdf)
- [AWS Cloud Practitioner Essentials (Second Edition)](https://aws.amazon.com/training/course-descriptions/cloud-practitioner-essentials/)
- [Flashcards](https://quizlet.com/275297341/amazon-cloud-practitioner-certification-flash-cards/)

### AWS Certified Architect
- https://aws.amazon.com/training/path-architecting/
- [AWS Certified Solution Architect - Associate 2019 Exam Notes](https://github.com/AlessioCasco/AWS-CSA-2019-study-notes)
- [https://cliffordandrewboyd.com/wordpress/wp-content/uploads/2018/10/eBook.pdf](https://cliffordandrewboyd.com/wordpress/wp-content/uploads/2018/10/eBook.pdf)
- [AWS Certified Solutions Architect Associate Exam Blueprint](https://d0.awsstatic.com/training-and-certification/docs-sa-assoc/AWS_certified_solutions_architect_associate_blueprint.pdf)
- [Exam Readiness: AWS Certified Solutions Architect – Associate (Digital)](https://www.aws.training/Details/Curriculum?id=20685)
- [AWS Certified Solutions Architect Official Study Guide](https://www.academia.edu/38282456/AWS_Certified_Solutions_Architect_Official_Study_Guide)

### AWS Certified DevOps Engineer - Professional
- [Exam Readiness: AWS Certified DevOps Engineer – Professional (Simplified Chinese)](https://www.aws.training/Details/eLearning?id=40861)

Three ways to use AWS
1. AWS Management Console
2. Command Line Interface (CLI)
3. Software Development Kits (SDKs)

Which of the following terms refers to the power of scale computing resources up or down easily?
- Elasticity

## Compute
### [EC2](ec2.md)

[Amazon Elastic Block Store (EBS)](ebs.md)

### Lightsail

### ECR[/ecr.md]

### ECS

### [EKS](eks.md)

### Lambda
Fulling managed serverless.

Q. You have configured an AWS Lambda function to launch an Amazon EC2 Linux instance each Sunday night to run a 30-minute batch job.

What would be the most reliable way to terminate the instance after it has completed the batch job?
- [x] Have the instance run "sudo shutdown now -h"
- Create an AWS Batch job configured to run once per week to terminate the instance with a known Tag

### Batch
### [Elastic Beanstalk](beanstalk.md)

### Serverless Application Repository
 
## Storage
### [S3](s3.md)
### EFS
### FSx
### [S3 Glacier](glacier.md)
### [Storage Gateway](storage-gateway.md)
### AWS Backup
 
## Database
### [RDS](rds.md)
### [DynamoDB](dynamodb.md)
### ElastiCache
### Neptune
### [Amazon Redshift](redshift.md)
### Amazon QLDB
### Amazon DocumentDB
 
## Migration & Transfer 
### AWS Migration Hub
### Application Discovery Service
### Database Migration Service
### Server Migration Service
### AWS Transfer for SFTP
### Snowball
### DataSync
 
## Networking & Content Delivery 
### [VPC](vpc.md)
### [CloudFront](cloudfront.md)
### [Route 53](route53.md)
### API Gateway
### [Direct Connect](direct-connect.md)
### AWS App Mesh
### AWS Cloud Map
### Global Accelerator

## Developer Tools 
### CodeStar
### CodeCommit[codecommit.md]

### CodeBuild
### CodeDeploy
### CodePipeline
### Cloud9
### X-Ray
 
## Customer Enablement 
### AWS IQ
### Support
### Managed Services
 
## Robotics
### AWS RoboMaker
 
## Blockchain
### Amazon Managed Blockchain
 
## Satellite
### Ground Station
 
## Management & Governance 
### AWS Organizations
### [CloudWatch](cloudwatch.md)
### AWS Auto Scaling
### CloudFormation
### CloudTrail
### Config
### OpsWorks
### Service Catalog
### Systems Manager
### Trusted Advisor
### Control Tower
### AWS License Manager
### AWS Well-Architected Tool
### Personal Health Dashboard
### AWS Chatbot
### Launch Wizard
 
## Media Services 
### Elastic Transcoder
### Kinesis Video Streams
### MediaConnect
### MediaConvert
### MediaLive
### MediaPackage
### MediaStore
### MediaTailor
### Elemental Appliances & Software
 
## Machine Learning 
### Amazon SageMaker
### Amazon Comprehend
### Amazon Forecast
### Amazon Lex
### Amazon Machine Learning
### Amazon Personalize
### Amazon Polly
### Amazon Rekognition
### Amazon Textract
### Amazon Transcribe
### Amazon Translate
### AWS DeepLens
### AWS DeepRacer
 
## Analytics
### Athena
### EMR
### CloudSearch
### Elasticsearch Service
### Kinesis
### QuickSight
### Data Pipeline
### AWS Data Exchange
### AWS Glue
### AWS Lake Formation
### MSK
 
## Security, Identity, & Compliance 
### IAM
### Resource Access Manager
### Cognito
### Secrets Manager
### GuardDuty
### Inspector
### Amazon Macie
### AWS Single Sign-On
### Certificate Manager
### Key Management Service
### CloudHSM
### Directory Service
### WAF & Shield
### Artifact
### Security Hub
 
## AWS Cost Management 
### AWS Cost Explorer
### AWS Budgets
### AWS Marketplace Subscriptions
 
## Mobile
### AWS Amplify
### Mobile Hub
### AWS AppSync
### Device Farm
 
## AR & VR 
### Amazon Sumerian
 
## Application Integration 
### Step Functions
### Amazon EventBridge
### Amazon MQ
### Simple Notification Service
### Simple Queue Service
### SWF
 
## Customer Engagement 
### Amazon Connect
### Pinpoint
### Simple Email Service
 
## Business Applications 
### Alexa for Business
### Amazon Chime
### WorkMail
 
## End User Computing 
### WorkSpaces
### AppStream 2.0
### WorkDocs
### WorkLink
 
## Internet of Things 
### IoT Core
### IoT 1-Click
### IoT Analytics
### IoT Device Defender
### IoT Device Management
### IoT Events
### IoT Greengrass
### IoT SiteWise
### IoT Things Graph
 
## Game Development 
### Amazon GameLift

## AWS Regions
Your company has deployed resources across several AWS regions. Your CTO has mandated that developers and operations can only use N.Virginia, Frankfurt and Mumbai as regions. She is particularly concerned with ensuring that any solution scales when AWS releases new regions. What should you do?
- Use a SCP at the root of the organization to block assignment of permissions to anything except the three regions. 

## Networking
What statement is true about Internet gateways?
- An Internet gateway is needed if you want to connect to AWS services outside of the VPC.

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
Question: Which of the following is true if you stop an **Amazon Elastic Compute Cloud (Amazon EC2)** instance with an Elastic IP address in an **Amazon Virtual Private Cloud (Amazon VPC)**?
- A. The instance is disassociated from its Elastic IP address and must be re-attached
when the instance is restarted.
- B. The instance remains associated with its Elastic IP address.
- C. The Elastic IP address is released from your account.
- D. The instance is disassociated from the Elastic IP address temporarily while you restart the instance.

Answer: B. In an Amazon VPC, an instance's Elastic IP address remains associated with an instance when the instance is stopped.

Question: How are you billed for an Elastic IP address?
- 1. Per second when associated with a running Amazon EC2 instance
- 2. Per hour when not associated with an Amazon EC2 instance
- 3. Per GiB for the amount of data that flows through them
- 4. Per network adapter based on the Amazon EC2 instance type

Answer: 2

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

## Database
Question: You are designing an e-commerce web application that will scale to potentially hundreds of thousands concurrent users. Which database technology is best suited to hold the session state for large numbers of concurrent users?
1. Relational database using [Amazon RDS]()
2. NoSQL database table using [Amazon DynamioDB]()
3. Data warehouse using [Amazon Redshift]()
4. [Amazon S3]()

Answer: 2. 

### 

### 

### [Amazon ElastiCache](elasticache.md)

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

### [Amazon Elastic MapReduce (Amazon EMR)](emr.md)

## Security, Identity, & Compliance
### [Identity and Access Management (IAM)](iam.md)

### Amazon Cognito
Which of the following statements best describes **Amazon Cognito**?
- It is a simple user-data synchronization and identity service that helps you securely manage and synchronize app data for your users across their mobile devices.

### [Key Management Service (KMS)](kms.md)
AWS KMS is a managed service that makes it easy for you to create and control the encryption keys used to encrypt your data.

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
[AWS Directory Service](https://aws.amazon.com/directoryservice/) is a managed service offering that provides directories that contain information about your organization, including users, groups, computers, and other resources.

### AWS Certificate Manager
AWS Certificate Manager is a service that lets organizations easily provision, manage, and deploy Secure Sockets Layer/Transport Layer Security (SSL/TLS) certificates for use with AWS Cloud services.

### AWS Web Application Firewall (WAF)
[AWS Web Application Firewall (WAF)]() helps protect web applications from common attacks and exploits that could affect application availability, compromise security, or consume excessive resources.

### CloudTrail(cloudtrail.md)

### Edge Locations

## Analytics
Question: Each month your company processes 200 TB of data in Amazon S3, taking 24 hours to complete. Which method is most cost-effective?
1. Copy the data to a persistent Amazon EMR cluster and run MapReduce jobs
2. Create an application that reads the information from  Amazon S3 and runs it through an Amazon Kinesis stream
3. Run a transient Amazon EMR cluster and run MapReduce jobs against the data directly in Amazon S3
4. Launch a d2.8xlarge (32 vCPU, 244 GB RAM) Amazon EC2 instance and run an application to read and process each object sequentially.

Answer: 3

### [Amazon Kinesis](kinesis.md)

### AWS Data Pipeline
AWS Data Pipeline is a web service that helps you reliably process and move data between different AWS compute and storage services, and also on-premises data sources, at specified intervals.

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
AWS CloudFormation is a service that helps you model and set up your AWS resources so that you can spend less time managing those resources and more time focusing on your applications that run in AWS.

Automate AWS resources provisioning.

### OpsWorks
IaC with Chef

[AWS OpsWorks]() is a configuration management service that helps you configure and operate applications using Chef.

## Serverless/FaaS
### [AWS Lambda](lambda.md)

## Monitoring
### 

## Application Services
### Amazon API Gateway
[Amazon API Gateway]() is a fully managed service that makes it easy for developers to create, publish, maintain, monitor, and secure APIs at any scale.

### Amazon Elastic Transcoder 
[Amazon Elastic Transcoder]() is media transcoding in the cloud.

### Amazon Simple Notification Service (SNS)
[Amazon Simple Notification Service (Amazon SNS)]() is a web service that coordinates and manages the delivery or sending of messages to recipients.

Flexible, fully managed **pub/sub messaging** and mobile communications service.

Q. What is an efficient way to fan-out a single Amazon SNS message to multiple Amazon SQS queues?
- Create multiple SQS queues that subscribe to the SNS topic.

Q. When can an Amazon SNS message be deleted after being published to a topic?
- Messages cannot be deleted

### Amazon Simple Email Service (Amazon SES)
[Amazon Simple Email Service (Amazon SES)]() is a cost-effective email service that organizations can use to send transactional email, marketing messages, or any other type of content to their customers.

### Amazon Simple Workflow Service (SWF)
[Amazon SWF]() makes it easy to build applications that coordinate work across distributed components.

Question: Which process in an [Amazon Simple Workflow Service (Amazon SWF)](https://aws.amazon.com/swf/) workflow implements a task?
- A. Decider
- B. Activity worker
- C. Workflow starter
- D. Business rule

Answer: B. An activity worker is a process or thread that performs the activity tasks that are part of your workflow. Each activity worker polls Amazon SWF for new tasks that are appropriate for that activity worker to perform; certain tasks can be performed only by certain activity workers. After receiving a task, the activity worker processes the task to completion and then reports to Amazon SWF that the task was completed and provides the result. The activity task represents one of the tasks that you identified in your application.

### [Amazon Simple Queue Service (SQS)](sqs.md)

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

Question: Which of the following are true about the AWS shared responsibility model? (Choose 3
answers)
- A. AWS is responsible for all infrastructure components (that is, AWS Cloud services) that support customer deployments.
- B. The customer is responsible for the components from the guest operating system upward (including updates, security patches, and antivirus software).
- C. The customer may rely on AWS to manage the security of their workloads deployed on AWS.
- D. While AWS manages security of the cloud, security in the cloud is the responsibility of the customer.
- E. The customer must audit the AWS data centers personally to confirm the compliance of AWS systems and services.

Answer: A, B, and D. In the AWS shared responsibility model, customers retain control of what
security they choose to implement to protect their own content, platform, applications,
systems, and networks, no differently than they would for applications in an on-site data
center.

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



 
