# AWS Direct Connect
AWS Direct Connect allows organizations to establish a dedicated network connection from
their data center to AWS. Using AWS Direct Connect, organizations can establish private
connectivity between AWS and their data center, office, or colocation environment, which in
many cases can reduce network costs, increase bandwidth throughput, and provide a more
consistent network experience than Internet-based VPN connections.

Q. Your company has recources in the cloud with AWS and in a data center, connected via [AWS Direct Connect](https://aws.amazon.com/directconnect/). You have applications in both locations that generate logs as messages and you wish to capture them and process them inside your AWS environment. How can you minimize effort and maintian security?
- Use AWS DirectSync over AWS Direct Connect to stream messagers to an Amazon S3 bucket. Use an Amazon Kinesis agent to process the messages.
- [x] Steam messages over AWS Direct Connect to a VPC Interface Endpoint bound to Amazon Kinesis.

Q. You have a hybrid IT application that requires access to Amazon DynamoDB. You have set up AWS Direct Connect between your data center and AWS. All data written to DynamoDB should be encrypted as it is written to the database. How will you enable connectivity from the on-premises application to DynamoDB?
- Set up a public [Virtual Interface (VIF)](https://docs.aws.amazon.com/directconnect/latest/UserGuide/WorkingWithVirtualInterfaces.html)

Q. Which of the following has the highest route priority in the Border Gateway Protocol (BGP) path selection algorithm used by AWS?
- Local routes to the VPC

