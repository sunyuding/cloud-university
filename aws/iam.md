# Identity and Access Management (IAM)
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