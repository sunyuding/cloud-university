# Identity and Access Management (IAM)
A principal is an IAM entity that is allowed
to interact with AWS resources. A principal can be permanent or temporary, and it can
represent a human or an application. There are three types of principals: 
- root users 
- IAM users
- roles/temporary security tokens


You web application requires temporary authorization to use AWS services. Which IAM entity should be used?
- Role

**Authorisation** is the process in which a system you have authenticated to establishes what you can
access and at what level.

Q. What additional method of Access Control can be assigned to an AWS user that utilises a random 6 digit number that is only available for a very short time period before the number changes?
- Multi Factor Authentication

Q. An application running on an Amazon EC2 instance wishes to make a call to an AWS API. What is the most secure way to provide AWS credentials to the application?
- Assign an IAM Role to the instance.

Q. Which feature of AWS is designed to permit calls to the platform from an Amazon EC2 instance without needing access keys placed on the instance?
- **IAM instance profiles** (You cannot attach IAM roles to EC2 instance)

Q. Which one of the following is true when using AWS IAM Groups?
- An IAM user can be a member of multiple groups.

Q. Who can create objects in an Amazon S3 bucket with this bucket policy?
```json
{
    "Version":
    "Statement": [
        {
            "Effect": "Deny"
        }
    ]
}
```
- Nobody

Question: You have an application that will run on an **Amazon Elastic Compute Cloud (Amazon EC2)** instance. The application will make requests to **Amazon Simple Storage Service (Amazon S3)** and **Amazon DynamoDB**. Using best practices, what type of **AWS Identity and Access Management (IAM)** identity should you create for your application to access the identified services?
- A. IAM role
- B. IAM user
- C. IAM group
- D. IAM directory

Answer: A. 
Don't create an IAM user (or an IAM group) and pass the user's credentials to the application or embed the credentials in the application. Instead, create an IAM role that you attach to the Amazon EC2 instance to give applications running on the instance temporary security credentials. The credentials have the permissions specified in the policies attached to the role. A directory is not an identity object in IAM.

Question: When a request is made to an AWS Cloud service, the request is evaluated to decide whether it should be allowed or denied. The evaluation logic follows which of the following rules? (Choose 3 answers)
- A. An explicit allow overrides any denies.
- B. By default, all requests are denied.
- C. An explicit allow overrides the default.
- D. An explicit deny overrides any allows.
- E. By default, all requests are allowed.

Answer: B, C, and D. When a request is made, the AWS service decides whether a given request
should be allowed or denied. The evaluation logic follows these rules:
- 1) By default, all requests are denied (in general, requests made using the account
credentials for resources in the account are always allowed).
- 2) An explicit allow overrides this default.
- 3) An explicit deny overrides any allows.

