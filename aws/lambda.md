# AWS Lambda
run serverless functions on AWS

Q. Your "www.example.com" domain is pointing to an Amazon EC2 instance. How could you keep this operating, but send requests for "www.example.com/news/" to an AWS Lambda function?
- Use an **Application Load Balancer** with a separate **Target Group**

Question: You have an AWS Lambda function that needs access to a public API on the Internet and also an Amazon RDS instance in a private subnet of an Amazon VPC. How do you configure such access?
1. Associate the Lambda function with a private subnet in the VPC and associate an Elastic IP address to the Elastic Network Interface
2. Launch a NAT Gateway in a public subnet and associate the Lambda function with a private subnet in the VPC
3. Associate the Lambda function with a public subnet in the VPC and create a VPC Endpoint for Amazon RDS
4. It is not possible to connect an AWS Lambda function simultaneously to a private subnet and the Internet

Answer: 2.

