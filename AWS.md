# AWS
- (Tutorial) Amazon AWS - https://aws.amazon.com/getting-started/tutorials/

- [ ] [A Beginner's Guide To Scaling To 11 Million+ Users On Amazon's AWS](http://highscalability.com/blog/2016/1/11/a-beginners-guide-to-scaling-to-11-million-users-on-amazons.html)


- [ ] [Amazon SQS (queue)](https://aws.amazon.com/sqs/)

- [ ] [Amazon SNS (pub-sub)](https://aws.amazon.com/sns/)

- [ ] [2007: Dynamo: Amazon’s Highly Available Key-value Store](http://s3.amazonaws.com/AllThingsDistributed/sosp/amazon-dynamo-sosp2007.pdf)

## Route53
- Route53 also has 100% uptime SLA, Elastic Load Balancing and VPC can also provide a level of resilience if required

NEW QUESTION 
Your application is currently running on Amazon EC2 instances behind a load balancer. Your management has decided to use a **Blue/Green deployment** strategy. How should you implement this for each deployment?

- A. Set up **Amazon Route 53** health checks to fail over from any Amazon EC2 instance that is currently being deployed to.
- B. Using AWS CloudFormation, create a test stack for validating the code, and then deploy the code to each production Amazon EC2 instance.
- C. Create a new load balancer with new Amazon EC2 instances, carry out the deployment, and then switch DNS over to the new load balancer using **Amazon Route 53** after testing.
- D. Launch more Amazon EC2 instances to ensure high availability, de-register each Amazon EC2 instance from the load balancer, upgrade it, and test it, and then register it again with the load balancer.

Answer: C

## VPC

## CodeCommit
### Setup permissions
https://youtu.be/W-SM4m19JMA

## ECR
Amazon Elastic Container Registry (ECR) is a fully-managed Docker container registry that makes it easy for developers to store, manage, and deploy Docker container images.c

## AWS Transfer for SFTP
AWS Transfer for SFTP is a fully managed service that enables the transfer of files directly into and out of Amazon S3 using the Secure File Transfer Protocol (SFTP)—also known as Secure Shell (SSH) File Transfer Protocol. 

## Certificates
- [ ] [A curated list of AWS resources to prepare for the AWS Certifications](https://gist.github.com/leonardofed/bbf6459ad154ad5215d354f3825435dc)
- [ ] [AWS Certified Solution Architect - Associate 2019 Exam Notes](https://github.com/AlessioCasco/AWS-CSA-2019-study-notes)
