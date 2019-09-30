-  Are looking for a logical and structured approach to problem solving through distributed systems, network and web scenarios. 
-  Make sure you understand the questions and ask appropriate follow-up questions to the interviewer when needed. 
-  A big part is finding out what the actual problem is and breaking it down into specifics. 

1. Identify the problem
    - Step1: what exactly is the problem?
        - listen or read carefully and take notes
        - who, what, and when
        - try repeating your understanding of the problem
2. Find the root cause
    - Step2: Gather more details, eliminate variables
        - Error messages
        - Events logs
        - Screenshots, video, or other supporting information
        - Diagnostics results
        - Monitoring
    - Step 3: Reproduce the problem, develop hypothesis of root cause

3. Provide solution
    - Step 4: Attempt a fix based on findings
    - Prepare for future issues
Read more: https://www.spiceworks.com/it-articles/troubleshooting-steps/

# GCP
For example if your web server goes down over the weekend, how do you get notified? Or how do you identify which IP address to blacklist, for your HTTP load balancer?
- What if your server goes down in the middle of the night or over the weekend? Do you expect someone to always look at dashboards to determine whether your servers are available? Or have enough capacity or bandwidth? 
    - If not, you want to create alerting policies that notify you when specific conditions are met
- Analyze logs in **BigQuery** and visualize in **Data Studio**

# Identifying and Troubleshooting Performance Issues
- Add **performance test** to your test suite to ensure that the performance of your application doesn't degrade when you fix bugs, add new features, or change underlying software.
## Check **performance watchpoints** related to incoming requests
- Web Authoring
    - Web page design and implemenation
        - **[Pagespeed Insights](https://developers.google.com/speed/)**
        - **Chrome DevTools**
- Cold-boot Performance
- Self-infliceted Load
    - Watch out for **self-inflicted load**. This is load caused by the application itself, such as **service-to-service** calls or **browser-to-service** calls. Check for self-inflicted load. This is load caused by the application itself, such as service-to-service or browser-to-service calls. For example, check for polling cron jobs, batch requests, or multiple Ajax requests from the browser. You can use client-side tools such as **Chrome DevTools** and server-side load analysis tools such as **Stackdriver** Trace to find the source of your problem.
## Review application code and logs
- Application Errors
    - Check logs for application errors, such as HTTP errors and exceptions. Identify the root cause of the log messages and confirm that they are not related to periodic load or performance issues. Prioritize investigation by the frequency of errors. Because this data is historical, some errors might have been intermittent or already resolved. If a log message is unreproducible, it might be better to do defer the investigation. 
- Runtime Code Generations
    - Aspect-oriented programming practices can sometimes cause reduced application performance. Consider compile-time code generation instead.
- Static Resources
    - Don't serve static resources from your application. Instead, use a content delivery network such as **Google Cloud CDN** with **Google Cloud Storage**.
- Caching
    - Database
- One-at-a-Time Retrieval 
    - Replace these individual requests with a single batch request or send a request in parallel. 
- Error-Handling
    - Don't retry constantly on errors. Instead, retry with **exponential backoff**. Implement a circuit breaker to stop retries after a certain number of failures. Note that you should only retry in case of errors such as connection timeouts or too many requests. Don't retry in case of errors such as 5xx errors and malformed URL errors and so on.

# Reference
-  Check out [Life in App Engine Production​](https://www.youtube.com/watch?v=rgQm1KEIIuc) for a troubleshooting example.
   - ["A distributed system is one in which the failure of a computer you didn’t even know existed can render your own computer unusable." - Leslie Lamport](https://www.microsoft.com/en-us/research/publication/distribution/)
   - Master/Slave
   - "Truse, but verify."
     - Strong checksums at many layers of the stack are best
   - Any given datacenter can be rendered unreachable or unfit for serving at any time, without warning
     - Un-isolated traffic can degrade performance
     - Power failure
     - Network partition
     - Infrastructure corrupts or isolates data
   - “To expect the unexpected shows a thoroughly modern intellect.” - Oscar Wilde
   - A service running in a given datacenter can be no more reliable than the least reliable component it utilizes
- [Troubleshooting Ubuntu Server](http://www.informit.com/articles/article.aspx?p=1381889)
  - [General Troubleshooting Philosophy](http://www.informit.com/articles/article.aspx?p=1381889)
  - [Localhost Troubleshooting](http://www.informit.com/articles/article.aspx?p=1381889&seqNum=2)
  - [Nerwork Troubleshooting](http://www.informit.com/articles/article.aspx?p=1381889&seqNum=3)
  - [Hardware Troubleshooting](http://www.informit.com/articles/article.aspx?p=1381889&seqNum=4)   
  
- [DevOps Troubleshooting: Linux® Server Best Practices](https://www.comcol.nl/code/inkijkexemplaar/9780321832047/devops-troubleshooting-engels-kyle-rankin.pdf)
- [Troubleshooting API requests | Postman Learning Center
](https://learning.getpostman.com/docs/postman/sending_api_requests/troubleshooting_api_requests)
- [REST API Troubleshooting Guide | Kinvey]()
- 5% API fail, how to troubleshoot

- [ ] [Here are seven of the most common web application performance roadblocks and how to fix them:](https://stackify.com/web-application-problems/)
1. DNS issues and network connectivity
2. Slow servers and loading time
3. Poorly written code
4. Lack of load balancing
5. Traffic spikes
6. Specific HTML title tags
7. Failing to optimize bandwidth Usage


TSE - Platform
Technical Troubleshooting
	1. Database 
	2. Network
	3. Web
	4. DNS

Web Tech
	1. Internet
	2. Browser
	3. LB
	4. CDN
	Performance

Code debugging/Programming
	
Client facing
	How to support a customer
	Sinerial
	Walk through a process

Cloud
	Cloud Storage

1. How you handle customer issues
    1. Communicate with engineers
    2. Troubleshooting - web tech
        1. Break down 
    3. Protocol error code

2. Specific knowledge
    1. Database
        1. SQL 
        2. SQL vs NoSQL
        3. Schema design
    2. Programming
    3. Debugging
    
3. Hiring manager
    1. Client-facing
    2. How do you work with teammate
    3. How do you work with the customers
    4. Leadership
    5. Putting customers first/ownership
    6. Assume some senatorial



