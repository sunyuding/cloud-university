# Amazon Route 53
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

Q. Which routing policy should you choose in order to achieve this?
- Geolocation routing

Q. Why is referencing an Application Load Balancer or Classic Load Balancer by its DNS CNAME recommended?
- IP addresses may change as the load balancer scales

