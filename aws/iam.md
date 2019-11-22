# Identity and Access Management (IAM)

## Principals
A principal is an IAM entity that is allowed to interact with AWS resources. A principal can be permanent or temporary, and it can represent a human or an application. There are three types of principals: 
- root users 
- IAM users
- roles/temporary security tokens

### Root User

### IAM Users
Question: Your security team is very concerned about the vulnerability of the IAM administrator user accounts (the accounts used to configure all IAM features and accounts). What steps can be taken to lock down these accounts? (Choose 3 answers)
- A. Add **multi-factor authentication (MFA)** to the accounts.
- B. Limit logins to a particular U.S. state.
- C. Implement a password policy on the AWS account.
- D. Apply a source IP address condition to the policy that only grants permissions when the user is on the corporate network.
- E. Add a CAPTCHA test to the accounts.

Answer: A, C, D. Neither B nor E are features supported by IAM.

### Roles/Temporary Security Tokens
AWS provides the actor with a temporary security token from the [AWS Security Token Service (STS)]() that the actor can use to access AWS Cloud services.

Question: Which of the following are based on temporary security tokens? (Choose 2 answers)
- A. Amazon EC2 roles
- B. MFA
- C. Root user
- D. Federation

Answer: A, D. **Amazon EC2 roles** provide a temporary token to applications running on the instance; **federation** maps policies to identities from other sources via temporary tokens.

#### Amazon EC2 Roles
Question: An application running on an Amazon EC2 instance wishes to make a call to an AWS API. What is the most secure way to provide AWS credentials to the application?

Answer: - Assign an **IAM Role** to the instance.

Question: Which of the following are benefits of using **Amazon EC2 roles**? (Choose 2 answers)
- A. No policies are required.
- B. Credentials do not need to be stored on the Amazon EC2 instance.
- C. Key rotation is not necessary.
- D. Integration with Active Directory is automatic.

Answer: B, C. Amazon EC2 roles must still be assigned a policy. Integration with Active Directory involves integration between Active Directory and IAM via SAML.

#### Cross-Account Access

#### Federation


## Authentication

You web application requires temporary authorization to use AWS services. Which IAM entity should be used?
- Role

## Authorisation
**Authorisation** is the process in which a system you have authenticated to establishes what you can access and at what level.

### Policies
JSON

### Associating Policies with Principals

---
Question: You want to grant the individuals on your network team the ability to fully manipulate Amazon EC2 instances. Which of the following accomplish this goal? (Choose 2 answers)
- A. Create a new policy allowing EC2:* actions, and name the policy NetworkTeam.
- B. Assign the managed policy, EC2FullAccess, to a group named NetworkTeam, and assign all the team members’ IAM user accounts to that group.
- C. Create a new policy that grants EC2:* actions on all resources, and assign that policy to each individual’s IAM user account on the network team.
- D. Create a NetworkTeam IAM group, and have each team member log in to the AWS Management Console using the user name/password for the group.

Answer: B, C. Access requires an appropriate **policy** associated with a **principal**. Response A is merely a policy with no principal, and response D is not a principal as IAM groups do not have user names and passwords. Response B is the best solution; response C will also work but it is much harder to manage.



### Multi-Factor Authentication (MFA)
Q. What additional method of Access Control can be assigned to an AWS user that utilises a random 6 digit number that is only available for a very short time period before the number changes?
- Multi Factor Authentication

### Rotating Keys

### Resolving Multiple Permissions
1. Initially the request is denied by default.
2. All the appropriate policies are evaluated; if there is an explicit “deny” found in any policy, the request is denied and evaluation stops.
3. If no explicit “deny” is found and an explicit “allow” is found in any policy, the request is allowed.
4. If there are no explicit “allow” or “deny” permissions found, then the default “deny” is maintained and the request is denied.

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

---
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

---
Question: Which of the following methods will allow an application using an AWS SDK to be authenticated as a principal to access AWS Cloud services? (Choose 2 answers)
- A. Create an IAM user and store the user name and password for the user in the
application’s configuration.
- B. Create an IAM user and store both parts of the access key for the user in the
application’s configuration.
- C. Run the application on an Amazon EC2 instance with an assigned IAM role.
- D. Make all the API calls over an SSL connection.

Answer: B, C. Programmatic access is authenticated with an access key, not with user names/passwords. IAM roles provide a temporary security token to an application using an SDK.

---
Question. Which of the following are found in an IAM policy? (Choose 2 answers)
A. Service Name
B. Region
C. Action
D. Password

Answer. A, C. IAM policies are independent of region, so no region is specified in the policy. IAM
policies are about authorization for an already-authenticated principal, so no password is
needed.

---
Question. Your AWS account administrator left your company today. The administrator had access
to the root user and a personal IAM administrator account. With these accounts, he
generated other IAM accounts and keys. Which of the following should you do today to
protect your AWS infrastructure? (Choose 4 answers)
- A. Change the password and add MFA to the root user.
- B. Put an IP restriction on the root user.
- C. Rotate keys and change passwords for IAM accounts.
- D. Delete all IAM accounts.
- E. Delete the administrator’s personal IAM account.
- F. Relaunch all Amazon EC2 instances with new roles.

Answer: A, B, C, E. Locking down your root user and all accounts to which the administrator had access is the key here. Deleting all IAM accounts is not necessary, and it would cause great disruption to your operations. Amazon EC2 roles use temporary security tokens, so relaunching Amazon EC2 instances is not necessary.

---
Question. Which of the following actions can be authorized by IAM? (Choose 2 answers)
- A. Installing ASP.NET on a Windows Server
- B. Launching an Amazon Linux EC2 instance
- C. Querying an Oracle database
- D. Adding a message to an Amazon Simple Queue Service (Amazon SQS) queue

Answer. B, D. IAM controls access to AWS resources only. Installing ASP.NET will require Windows operating system authorization, and querying an Oracle database will require Oracle authorization.

