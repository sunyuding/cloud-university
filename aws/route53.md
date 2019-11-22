# Amazon Route 53
Amazon Route 53 is a highly available and scalable cloud DNS web service that is designed to give developers and businesses an extremely reliable and cost-effective way to route end users to Internet applications.

- Route53 also has 100% uptime SLA, Elastic Load Balancing and VPC can also provide a level of resilience if required

## Record Types
- Start of Authority (SOA) Record

## Routing Policy:
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

---
Q. Your company has its primary production site in North America and its DR site in Asia. You need to configure DNS so that if your primary site becomes unavailable, you can fail DNS over to the secondary site. Which DNS routring policy would best achieve this?
- **Failover routing**

---
Q. You have an application that for legal reasons must be hosted in the United States when US citizens access it. The application must be hosted in the European Union when citizens of the EU access it. For all other citizens of the world, the application must be hosted in Sydney.

---
Q. Which routing policy should you choose in order to achieve this?
- Geolocation routing

---
Q. Why is referencing an Application Load Balancer or Classic Load Balancer by its DNS CNAME recommended?
- IP addresses may change as the load balancer scales

---
Question: Which DNS record should you use to configure the transmission of email to your intended mail server?
1. SOA records
2. A records
3. MX records
4. CNAME records

Answer: 3.

---
Question: Which type of record is commonly used to route traffic to an IPv6 address?
- A. An A record
- B. A CNAME
- C. An AAAA record
- D. An MX record

Answer: C. An [AAAA record]() is used to route traffic to an IPv6 address, whereas an [A record]() is used to route traffic to an IPv4 address.

--- 
Question: Where do you register a domain name?
- A. With your local government authority
- B. With a domain registrar
- C. With InterNIC directly
- D. With the Internet Assigned Numbers Authority (IANA)

Answer: B. Domain names are registered with a [domain registrar](), which then registers the name to InterNIC.

--- 
Question: You have an application that for legal reasons must be hosted in the United States when U.S. citizens access it. The application must be hosted in the European Union when citizens of the EU access it. For all other citizens of the world, the application must be hosted in Sydney. Which routing policy should you choose in order to achieve this?
- A. Latency-based routing
- B. Simple routing
- C. Geolocation routing
- D. Failover routing

Answer: You should route your traffic based on where your end users are located. The best routing policy to achieve this is geolocation routing.

---
Which type of DNS record should you use to resolve an IP address to a domain name?
- A. An A record
- B. A C Name
- C. An SPF record
- D. A PTR record

Answer: D. A [PTR record]() is used to resolve an IP address to a domain name, and it is commonly referred to as “reverse DNS.”

--- 
You host a web application across multiple AWS regions in the world, and you need to configure your DNS so that your end users will get the fastest network performance possible. Which routing policy should you apply?
- A. Geolocation routing
- B. Latency-based routing
- C. Simple routing
- D. Weighted routing

Answer: B. You want your users to have the fastest network access possible. To do this, you would use [latency-based routing](). Geolocation routing would not achieve this as well as latencybased routing, which is specifically geared toward measuring the latency and thus would direct you to the AWS region in which you would have the lowest latency.

---
Question: Which DNS record should you use to configure the transmission of email to your intended mail server?
- A. SPF records
- B. A records
- C. MX records
- D. SOA record

Answer: C. You would use [Mail eXchange (MX) records]() to define which inbound destination mail server should be used.

---
Question: Which DNS records are commonly used to stop email spoofing and spam?
- A. MX records
- B. SPF records
- C. A records
- D. C names

Answer: B. SPF records are used to verify authorized senders of mail from your domain.

---
Question: You are rolling out A and B test versions of a web application to see which version results in the most sales. You need 10 percent of your traffic to go to version A, 10 percent to go to version B, and the rest to go to your current production version. Which routing policy should you choose to achieve this?
- A. Simple routing
- B. Weighted routing
- C. Geolocation routing
- D. Failover routing

Answer: B. Weighted routing would best achieve this objective because it allows you to specify which percentage of traffic is directed to each endpoint.

---
Question: Which DNS record must all zones have by default?
- A. SPF
- B. TXT
- C. MX
- D. SOA

Answer: D. The start of a zone is defined by the [SOA](https://en.wikipedia.org/wiki/SOA_record); therefore, all zones must have an SOA record by default.

---
Question: Your company has its primary production site in Western Europe and its DR site in the Asia Pacific. You need to configure DNS so that if your primary site becomes unavailable, you can fail DNS over to the secondary site. Which DNS routing policy would best achieve this?
- A. Weighted routing
- B. Geolocation routing
- C. Simple routing
- D. [Failover routing](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/routing-policy.html#routing-policy-failover)

Answer: D. Failover-based routing would best achieve this objective.

---
Question: Which type of DNS record should you use to resolve a domain name to another domain name?
- A. An A record
- B. A [CNAME record](https://support.google.com/a/answer/112037)
- C. An SPF record
- D. A PTR record

Answer: B. The CNAME record maps a name to another name. It should be used only when there are no other records on that name.

---
Question: Which is a function that Amazon Route 53 does not perform?
- A. Domain registration
- B. DNS service
- C. Load balancing
- D. Health checks

Answer: C. Amazon Route 53 performs three main functions: **domain registration**, **DNS service**, and **health checking**.

---
Question: 