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

Question: Which Amazon Elastic Compute Cloud (Amazon EC2) pricing model allows you to pay a set hourly price for compute, giving you full control over when the instance launches and terminates?
- A. Spot instances
- B. Reserved instance
- C. On Demand instances
- D. Dedicated instances

Answer: C. You pay a set hourly price for an On Demand instance from when you launch it until you explicitly stop or terminate it. Spot instances can be terminated when the spot price goes above your bid price. Reserved instances involve paying for an instance over a oneor three-year term. Dedicated instances run on hardware dedicated to your account and are not a pricing model.

Question: Under what circumstances will Amazon Elastic Compute Cloud (Amazon EC2) instance store data not be preserved?
- A. The associated security groups are changed.
- B. The instance is stopped or rebooted.
- C. The instance is rebooted or terminated.
- D. The instance is stopped or terminated.
- E. None of the above

Answer: D. The data in an instance store persists only during the lifetime of its associated instance. If an instance is stopped or terminated, then the instance store does not persist. Rebooting an instance does not shut down the instance; if an instance reboots (intentionally or unintentionally), data on the instance store persists. Security groups have nothing to do with the lifetime of an instance and have no effect here.

Question: Your web application needs 4 Amazon EC2 instances to support steady traffic nearly all of the time. On the last day of each month, the traffic triples.

What is the most cost effective way to handle this traffic pattern?
- Run 4 Researved Instances constantly, then add 8 On-Demand Instances on the last day of each month

Question: Which of the following are the minimum required elements to create an **Auto Scaling** launch configuration?
1. Launch configuration name, Amazon Machine Image (AMI), instance type
2. Launch configuration name, Amazon Machine Image (AMI), instance type, key pair
3. Launch configuration name, Amazon Machine Image (AMI), instance type, key pair, security group
4. Launch configuration name, Amazon Machine Image (AMI), instance type, key pair, security group, block device mapping

Answer: 1.

Question: An Amazon EC2 instance is being underutilized so you decide to down-size the instance. You Stop the instance and change its Instance Type. However, you are unable to Start the instance again because it is now in a Terminated state,. What caused the instance to Terminate?
1. It was using Instance Store for the boot volume
2. It was a Spot Instance
3. The instance had been launched using Auto Scaling
4. It was using a capacity reservation that was no longer available

Answer: 3.
