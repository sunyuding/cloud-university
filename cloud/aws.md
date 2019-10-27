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

Three ways to use AWS
1. AWS Management Console
2. Command Line Interface (CLI)
3. Software Development Kits (SDKs)

Which of the following terms refers to the power of scale computing resources up or down easily?
- Elasticity

## Computing
### Amazon Elastic Cloud Compute (EC2)
IaaS

What are the benefits of using Amazon EC2 instances compared to physical servers in your infrastructure? 
- Pay only for the capacity you use
- The ability to have different storage requirements

Purchase types:
- On-demand instances:
    - Compute capacity by the hour and second
    - Minimum of 60 seconds
- Reserved instances:
    - Low or no up-front payment instances reserved
    - Discount on hourly charge for that instance
- Spot instances:
    - Bid for unused Amazon EC2 capacity
    - Spot instances are spare EC2 capacity that can save you up 90% off of On-Demand prices that AWS can interrupt with a 2 minute notification. Spot uses the same underlying EC2 instances as On-Demand and Reserved Instances, and is best suited for fault-tolerant, flexible workloads.

When does the billing process for an Amazon EC2 system begin?
- It starts when the Amazon EC2 transitions to the running state.

An **Amazon Machine Image (AMI)** can be best described as a preconfigured template for your instances.

The function of **Key Pairs** is to encrypt the login information for Linux and Windows EC2 instances, and then decrypt the same information allowing you to authenticate onto the instance.

Q. Which Amazon EC2 feature ensures that your instances will not share a **physical** host with instances from any other AWS customer?
- Dedicated Instances

You need to create an Amazon EC2 instance with the fastest possible boot time. Which is the most appropriate solution?
- An Amazon EBS-backed AMI with no user data

Q. You have a relational database that is running on a Windows Amazon Elastic Compute Cloud(Amazon EC2) instance. What would be the best choice for storage?
- **Provisioned IOPS**

Q. You have an Amazon EC2 instance that was launched from an Community AMI. You have received notice that this AMI is about to be deleted.

How can you ensure that your instance will continue to run after the AMI is deleted?
- The AMI deletion will not affect your instance.

## Amazon Elastic Block Store (EBS)

- Three volume types:
    - General Purpose (SSD)
    - Provisioned IOPS (SSD)
    - Magnetic
- Persistent and customizable block storage for EC2 instances
- Replicated in the same Availability Zone
- Backup using Snapchots
- Easy and transparent Encryption
- Elastic volumes
- EBS volumes persist beyond the life of an EC2 instance

Check which EBS was attached to the instance.
```bash
$ lsblk
xvda ...
xvdb ...
```

```
$ mke2fs /dev/xvdb
$ sudo !!
```

Q. You need to take a snapshot of an Amazon Elastic Block Store(Amazon EBS) volume. How long will the volume be unavailable?
- The volume will be available immediately.

Q. To help prevent data loss due to the failure of any single hardware component, Amazon Elastic Block Storage (Amazon EBS) automatically replicates EBS volume data to which one of the following?
- Within the same **Availability Zone** in a region.




## Amazon Simple Storage Service (S3)
Q: How durable is Amazon S3?

Amazon S3 Standard, S3 Standard–IA, S3 One Zone-IA, and S3 Glacier are all designed to provide 99.999999999% durability of objects over a given year.

Standard Storage:
- 99.999999999% durability
- 99.99% availability

Standard-Infrequent Access (S-IA):
- 99.999999999% durability
- 99.9% availability

|Type|Durability|Availability|
|----|----------|------------|
|S3 Standard storage |99.999999999%|99.99%|
|Standard-Infrequent Access (S-IA) storage|99.999999999%|99.9%|
|S3 One Zone-IA storage|99.999999999%|99.5%|

Q: How reliable is Amazon S3?

The **S3 Standard storage** class is designed for 99.99% availability, the **S3 Standard-IA storage** class is designed for 99.9% availability, and the **S3 One Zone-IA storage** class is designed for 99.5% availability. 

https://aws.amazon.com/s3/faqs/

Storage cost:
- Number and size of objets
- Type of storage

Estimate S3 charges:
- Storage Class
- Storage (the number and size of objects stored in your S3 bucket)
- Requests (the number and type of requests)
- Data transfer (the amount of data transferred out of the S3 region)


Q. Which components of the AWS infrastructure can be decsribed as multiple, isolated locations within one geographic area?
- Avaliability Zones

Q. A user has archived data from Amazon S3 to Amazon Glacier. How much data can be restored by the user for free every month?
- 5% of archived data

Q. What are some reasons to enable **cross-region replication** on an Amazon S3 bucket?(Choose 2 answers)
- You have a set of users or customers who can access the second bucket with lower latency.
- For compliance reasons, you need to store data in a location at least 300 miles away from the first region.

Q. You are running a photo sharing website. Users need to be able to retrieve and display any image. On average, most images are requested only once or twice a year. 

Q. What would be the most cost-effective, highly available method of storing the images?
- [x] Save images on Amazon S3 as **Standard-Infrequent Access**
- [] Save images on Amazon S3 as **Glacier Deep Archive**

Q. You are running a photo sharing website with images being served directly from Amazon S3. Users can control whether their photos are public, private or shared amongst nominated friends. How can your application implement these access controls?
- Generate pre-signed URLs for each photo access.

Q. Your company legal team has been advised that some data in Amazon S3 might be required for a pending legal case. You therefore activate **Amazon S3 Object Lock Legal Hold**. When can this object be deleted?
- The object can be deleted by deactivating Legal Hold.

## AWS Regions
Your company has deployed resources across several AWS regions. Your CTO has mandated that developers and operations can only use N.Virginia, Frankfurt and Mumbai as regions. She is particularly concerned with ensuring that any solution scales when AWS releases new regions. What should you do?
- Use a SCP at the root of the organization to block assignment of permissions to anything except the three regions. 

## Networking
What statement is true about Internet gateways?
- An Internet gateway is needed if you want to connect to AWS services outside of the VPC.

### Amazon Virtual Private Cloud (VPC)
- Builds upon high availability of AWS Regions adn Availability Zones (AZ)
    - Amazon VPC lives within a region
- Subnets
    - Used to divide Amazon VPC
- Route tables
    - Control traffic going out of the subnets
- Internet Gateway (IGW)
    - Allows access to the Internet from Amazon VPC
- NAT Gateway
    - Allows private subnet resources to access Internet
- Network Access Control Lists (NACL)
    - Control access to subnets

Which of the following statements is true of Amazon Virtual Private Clouds (VPC)?
- You can create many subnets in a VPC, though fewer is recommended to limit complexity

What aspect of an Amazon VPC is stateful?
- Security Groups

### Security Groups
Act as built-in **firewalls**. 

An Amazon VPC security group can be associated with:
- An Elastic Network Interface

### AWS VPN
- AWS Site-to-Site VPN
    - Static
    - Dynamic
- AWS Client VPN

### Elastic Load Balancer 
Q. What is the difference between an Internet-facing load balancer and an internal-facing load balancer?
- The DNS name of an Internet-facing load balancer resolves to a public IP address while an internal-facing load balancer resolves to a private IP address. 

#### Application Load Balancer
Why use the ALB?
- One is the ability to use containers to host your micro services and route to those applicaitons from a single load balancer.
- ALB allows you to route different requests to the same instance, but differ the path based on the port. 

- Listener
- Target
- Target Group

- Path-based provides rules that forward requests to different target groups
- Host-based can be used to define rules that forward requests to different target groups based on host name

You have an application composed of individual services. You need to route a request to a service based on the content of the request. Which service should you use?
- Elastic Load Balancing

Your web application runs on multiple Amazon EC2 instances behind an Application Load Balancer. The load balancer is configured to perform health checks on the EC2 instances.

If an instance fails to pass health checks, which statement will be true?
- The load balancer stops sending traffic to the instance that failed its health check.

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

### Amazon Route 53
- Route53 also has 100% uptime SLA, Elastic Load Balancing and VPC can also provide a level of resilience if required

Routing Policy:
- Simple routing policy
- Failover routing policy
- Geolocation routing policy
- Geoproximity routing policy 
- Latency routing policy
- Multivalue answer routing policy
- Weighted routing policy

NEW QUESTION 
Your application is currently running on Amazon EC2 instances behind a load balancer. Your management has decided to use a **Blue/Green deployment** strategy. How should you implement this for each deployment?

- A. Set up **Amazon Route 53** health checks to fail over from any Amazon EC2 instance that is currently being deployed to.
- B. Using AWS CloudFormation, create a test stack for validating the code, and then deploy the code to each production Amazon EC2 instance.
- C. Create a new load balancer with new Amazon EC2 instances, carry out the deployment, and then switch DNS over to the new load balancer using **Amazon Route 53** after testing.
- D. Launch more Amazon EC2 instances to ensure high availability, de-register each Amazon EC2 instance from the load balancer, upgrade it, and test it, and then register it again with the load balancer.

Answer: C

Q. How is storage typically priced on AWS Cloud?
- Charged per GB

Q. Your company has its primary production site in North America and its DR site in Asia. You need to configure DNS so that if your primary site becomes unavailable, you can fail DNS over to the secondary site. Which DNS routring policy would best achieve this?
- **Failover routing**

Q. You have an application that for legal reasons must be hosted in the United States when US citizens access it. The application must be hosted in the European Union when citizens of the EU access it. For all other citizens of the world, the application must be hosted in Sydney.

Which routing policy shoudl you choose in order to achieve this?
- Geolocation routing

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
- Use **ElastiCache** to cache frequently used data. Update the application logic to read/write from the cache.

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

### Amazon Simple Queue Service (SQS)
Q. You are working with your application development team and have created an Amazon Simple Queue Service (Amazon SQS) standard queue. Your developers are complaining that messages are being processed more than once. What can you do to limit or stop this behavior?
- Deploy a **First-In, First-Out (FIFO) queue** and have the developers point their application to it.

Q. How can you grant a different AWS account permission to send messages to your Amazon SQS queuue?
- "Create an IAM User for the other account and add an IAM policy that grants access to the queue." is incorrect. Cross-account access need to create a role.
- Create an Amazon SQS policy that grants the other account access. 

### Amazon Simple Notification Service (SNS)
Flexible, fully managed **pub/sub messaging** and mobile communications service.

### Amazon CloudFront
CDN. Speeds up the delivery of your content to viewers across the globe.

## CodeCommit
### Setup permissions
https://youtu.be/W-SM4m19JMA

## ECR
Amazon Elastic Container Registry (ECR) is a fully-managed Docker container registry that makes it easy for developers to store, manage, and deploy Docker container images.

```
aws ecr get-login --region us-west-2 --no-include-email --profile=engineering
```

[Using the AWS CLI with Amazon ECR](https://docs.aws.amazon.com/AmazonECR/latest/userguide/ECR_AWSCLI.html)

## Amazon Elastic Kubernetes Service (EKS)
- [Amazon EKS Workshop](https://eksworkshop.com)
- [Amazon Elastic Container Service for Kubernetes (EKS) Primer](https://www.aws.training/Details/eLearning?id=32894)
- Contianer management platform
    - Amazon Elastic Container Service (ECS)
    - Docker Swarm
    - [kubernetes](/kubernetes.md)
- Cluster Autoscaler for AWS provides integration with Auto Scaling groups.
- AWS manage the **control plane**
- You take care of provisioning, updating, scaling, patching the **data plane**
- master
    - Controller manager
    - Cloud controler
    - Scheduler
- worker
- ReplicaSets
- kubectl
- Dashboard

What is the basic unit of deployment in Kubernetes?
- Pods

What is a Kubernetes service?
- A logical collection of pods and a means to access them

![](codepipeline.png)

What form of Kubernetes does EKS support?
- Native, upstream Kubernetes

Which components are managed by EKS?
- The Kubernetes control plane (master)

Customers are responsible for managing the EKS work nodes.

What is the recommended method to update EKS worker nodes to a new version of Kubernetes?
- Replace the nodes with the new AMI and migrate your pods to the new group.

What type of service can be accessed from outside the cluster?
- NodePort
- LoadBalancer

![](auth.png)

![](sso.png)

### Secrets

How are secrets in **Secrets Manager** usually accessed?
- Through **System Manager Parameter Store**

### eksctl
eksctl is an open source tool for managing EKS clusters developed by Weaveworks and AWS

[LAUNCH USING EKSCTL](https://eksworkshop.com/eksctl/)

```
eksctl is a tool jointly developed by AWS and Weaveworks that automates much of the experience of creating EKS clusters.
```

```
$ eksctl create cluster -f example.yaml
```

- Autoscaling node groups
    - Define a maximum and minimum number of nodes and scale based on cluster load.

https://github.com/fluxcd/multi-tenancy

https://eksctl.io/

### upgrade
You are responsible for updating the EKS **worker node**.

There are 2 ways
1. Node group
2. CloudFormation

What is the recommended method to update EKS worker nodes to a new version of Kubernetes?
- Replace the nodes with the new AMI and migrate your pods to the new group.

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



## Identity and Access Management (IAM)
You web application requires temporary authorization to use AWS services. Which IAM entity should be used?
- Role

**Authorisation** is the process in which a system you have authenticated to establishes what you can
access and at what level.

Q. What additional method of Access Control can be assigned to an AWS user that utilises a random 6 digit number that is only available for a very short time period before the number changes?
- Multi Factor Authentication

Q. An application running on an Amazon EC2 instance wishes to make a call to an AWS API. What is the most secure way to provide AWS credentials to the application?
- Assign an IAM Role to the instance.

Q. Which feature of AWS is designed to permit calls to the platform from an Amazon EC2 instance without needing access keys placed on the instance?
- **IAM instance profiles** (You cannot attach IAM roles to EC2 instance)

Q. Which one of the following is true when using AWS IAM Groups?
- An IAM user can be a member of multiple groups.

## AWS Directory Service
https://aws.amazon.com/directoryservice/

## AWS Shield
**AWS Shield** is a managed **Distributed Denial of Service (DDoS)** protection service that safeguards applications running on AWS.
- AWS Shield Standard
    - Automatic protection
- AWS Shield Advanced
    - Specialized support

## AWS Config
Which statement is true about AWS Config and Regions?
- AWS Config is a Region specific service, meaning it has to be configured in every region you wish to use it

## CloudTrail
Which other AWS service can you use to enable greater security of your CloudTrail log files?
- Key Management Service (KMS)
_The use of AWS KMS is an optional element of CloudTrail, but it allows additional
encryption to be added to your Log files when stored on S3_

The AWS CloudTrail service provides which of the following?
- Logs of the API requests for AWS resources within your account

## Key Management Service (KMS)
How is Key Management Service (KMS) priced?
- KMS is priced per customer master key and the number of requests received per month. _Explanation: KMS is priced per two factors: the number of Customer Master Keys maintained in
KMS and the number of requests received within a month._

Q. Your company as a policy of rotating Access Keys each quarter. How can you rotate Access Keys with minimal impact on your applications?
- Create an additional Access Key. Update the applications with the new Access Key, then delete the old Access Key.

Q. Which of the following is true when using AWS Key Management Service(AWS KMS)?
- Use of keys is protected by access control policies defined and managed by you.

## Edge Locations

## Amazon Cognito
Which of the following statements best describes **Amazon Cognito**?
- It is a simple user-data synchronization and identity service that helps you securely manage and synchronize app data for your users across their mobile devices.

## Amazon Kinesis Data Firehose
What service will enable you to ingest this this stream of data and store it to Amazon S3 for future processing?
- **Amazon Kinesis Data Firehose**

Q. Your company has recources in the cloud with AWS and in a data center, connected via AWS Direct Connect. You have applications in both locations that generate logs as messages and you wish to capture them and process them inside your AWS environment. How can you minimize effort and maintian security?


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

## Monitoring
### Amazon CloudWatch
- Collect and track metrics
- Collect and monitor log files
- Set alarms
- Automatically react to changes

Schedule automated actions that self-trigger at certain times using Cron or rate expressions.
 
Q. You have misconfigured an Amazon EC2 instance's clock and are sending data to Amazon CloudWatch via the API. Because of the misconfigurawtion,logs are being sent 60 minutes in the future. Which of the following is true?
- Amazon CloudWatch will process the data.
    - 2 hrs in the future

Q. Using the Free Tier, what is the frequency of Amazon EC2 monitoring provided by Amazon CloudWatch?
- 5 minutes

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