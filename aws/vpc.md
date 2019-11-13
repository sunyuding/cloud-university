# Amazon Virtual Private Cloud (VPC)
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

Q. Which of the following statements is true of Amazon Virtual Private Clouds (VPC)?
- You can create many subnets in a VPC, though fewer is recommended to limit complexity

Q. What aspect of an Amazon VPC is stateful?
- Security Groups

Q. You have an application running on multiple Amazon EC2 instances in a single Availability Zone. The application calls a third-party API via the Internet. How can you provide the thrid-party with a single IP address to add to an access whitelist?
- Put the instances behind a NAT Gateway

Q. Two teams in your company are using separate AWS accounts that were allocated using AWS Organizations. How can both teams launch Amazon EC2 instances in the same VPC? 
- Use **VPC Sharing** to share a subnet between the accounts.

Q. You have an Amazon VPC being used only for Dev/Test purposes. The VPC is connected to your data center via [AWS Direct Connect](). The VPC does not have an Internet Gateway attached. How can you provide applications running on Amazon EC2 instances with access to Amazon S3 without going via your data center?
1. Direct traffic via a secondary ENI in another subnet
2. Use a NAT Gateway to forward requests to Amazon S3
3. [x] Create a [VPC Endpoint](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-endpoints.html) for Amazon S3
4. It is not possible to access Amazon S3 without an Internet Gateway

Q. Which one of the following is a security benefit of **VPC Endpoints**?
1. They provide private connectivity that increases performance to AWS Cloud services.
2. They limit access to services from the Internet, reducing who can access the APIs and services that AWS provides.
3. They provide greater availability and reliability than public endpoints, which increases security by limiting access for DDOS attacks.
4. [x] They provide private access, limiting the number of instances that require Internet access. 

Q. You have the [enableDnsHostname](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-dns.html) attribute set to true for your VPC. However, your Amazon EC2 instances are not receiving DNS hostnames. What could be the potential cause?
- [enableDnsSupport](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-dns.html) is not set to true

Question: An Amazon Elastic Compute Cloud (Amazon EC2) instance in an Amazon Virtual Private Cloud (Amazon VPC) subnet can send and receive traffic from the Internet when which of the following conditions are met? (Choose 3 answers)
- A. **Network Access Control Lists (ACLs)** and security group rules disallow all traffic except relevant Internet traffic.
- B. Network ACLs and security group rules allow relevant Internet traffic.
- C. Attach an **Internet Gateway (IGW)** to the Amazon VPC and create a subnet route table to send all non-local traffic to that IGW.
- D. Attach a Virtual Private Gateway (VPG) to the Amazon VPC and create subnet routes to send all non-local traffic to that VPG.
- E. The Amazon EC2 instance has a public IP address or **Elastic IP (EIP)** address.
- F. The Amazon EC2 instance does not need a public IP or Elastic IP when using Amazon VPC.

Answer: B, C, and E. 

You must do the following to create a public subnet with Internet access:
- Attach an IGW to your Amazon VPC.
- Create a subnet route table rule to send all non-local traffic (for example, 0.0.0.0/0) to the IGW.
- Configure your network ACLs and security group rules to allow relevant traffic to flow to and from your instance.

You must do the following to enable an Amazon EC2 instance to send and receive traffic from the Internet:
- Assign a public IP address or EIP address.

Question: If you launch five Amazon Elastic Compute Cloud (Amazon EC2) instances in an Amazon Virtual Private Cloud (Amazon VPC) without specifying a security group, the instances will be launched into a **default security group** that provides which of the
following? (Choose 3 answers)
- A. The five Amazon EC2 instances can communicate with each other.
- B. The five Amazon EC2 instances cannot communicate with each other.
- C. All inbound traffic will be allowed to the five Amazon EC2 instances.
- D. No inbound traffic will be allowed to the five Amazon EC2 instances.
- E. All outbound traffic will be allowed from the five Amazon EC2 instances.
- F. No outbound traffic will be allowed from the five Amazon EC2 instances.

Answer: A, D, and E. If a security group is not specified at launch, then an Amazon EC2 instance will be launched into the default security group for the Amazon VPC. The default security group allows communication between all resources within the security group, allows all outbound traffic, and denies all other traffic.


## Network Address Translation (NAT) Instances and NAT Gateways

### NAT Instance
A [network address translation (NAT) instance](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_NAT_Instance.html) is an Amazon Linux Amazon Machine Image (AMI) that is designed to accept traffic from instances within a private subnet, translate the source IP address to the public IP address of the NAT instance, and forward the traffic to the IGW.

### NAT Gateway
A [NAT gateway](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-nat-gateway.html) is an Amazon managed resource that is designed to operate just like a NAT instance, but it is simpler to manage and highly available within an Availability Zone.

## Virtual Private Gateways (VPGs), Customer Gateways (CGWs), and Virtual Private Networks (VPNs)

