# Elastic Load Balancer 

Q. What is the difference between an Internet-facing load balancer and an internal-facing load balancer?
- The DNS name of an Internet-facing load balancer resolves to a public IP address while an internal-facing load balancer resolves to a private IP address. 

Q. Which type of Elastic Load Balancer allows **path-based routing** for selecting the destination target group?
- **Application Load Balancer**

Question: **Elastic Load Balancing** allows you to distribute traffic across which of the following?
- A. Only within a single Availability Zone
- B. Multiple Availability Zones within a region
- C. Multiple Availability Zones within and between regions
- D. Multiple Availability Zones within and between regions and on-premises virtualized instances running OpenStack

Answer: B. The **Elastic Load Balancing** service allows you to distribute traffic across a group of Amazon Elastic Compute Cloud (Amazon EC2) instances in one or more Availability Zones within a region.

## Application Load Balancer
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