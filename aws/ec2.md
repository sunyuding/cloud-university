# Amazon Elastic Cloud Compute (EC2)
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

Q. What is the minimum number of Amazon EC2 instances required in an Auto Scaling group?
- Zero

Q. Your account has a regional **Reserved Instance** for one Amazon Linux m5.2xlarge instance type. However, you have been running a m5.4xlarge instance instead. This was the only instance being used ini the account. How will the usage of the m5.4xlarge be charged?
- It will be charged at half the normal on-demand price


Question: Under a single AWS account, you have set up an [Auto Scaling](https://aws.amazon.com/autoscaling/) group with a maximum capacity of 50 Amazon Elastic Compute Cloud (Amazon EC2) instances in us-west-2. When you scale out, however, it only increases to 20 Amazon EC2 instances. What is the likely cause?
- A. Auto Scaling has a hard limit of 20 Amazon EC2 instances.
- B. If not specified, the Auto Scaling group maximum capacity defaults to 20 Amazon EC2 instances.
- C. The Auto Scaling group desired capacity is set to 20, so Auto Scaling stopped at 20 Amazon EC2 instances.
- D. You have exceeded the default Amazon EC2 instance limit of 20 per region.

Answer: D. Auto Scaling may cause you to reach limits of other services, such as the default number of Amazon EC2 instances you can currently launch within a region, which is 20.

