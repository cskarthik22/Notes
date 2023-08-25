<img width="752" alt="image" src="https://github.com/cskarthik22/Notes/assets/38231831/3c1e5f4b-9646-4ea1-a38a-91813d7dd2c4">

## More Advance Concepts

* IAM Policies lives with
  1. IAM Users
  2. IAM Groups
  3. IAM Roles - tied with
      1. Trust Policy
      2. Permission Policy
  Note: Identity Policy - Controls what that identity can access.
* Resource Policy - Controls who can access that resource - it has additional attribute in JSON - called Principle.
  In resource-based policies in AWS, the "principal" element is used to specify which external identities are allowed to access the associated resource. The principle can have different values depending on the type of resource it is associated with. It can be an AWS account (identified by a 12-digit account ID), an IAM user, a federated user, another IAM role, or even another AWS service. By configuring the principle in the resource policy, you can control and define the specific external identities that have permission to access the resource. This provides an extra mechanism for managing access to AWS resources beyond identity-based policies, which are associated with IAM users and groups.
  Example: Some services allow storing policy with resources
    1. S3 ( Bucket policy )
    2. Amazon Glacier ( Vault policy )
    3. Amazon SNS ( Topic policy )
    4. Amazon SQS ( Queue policy )
* Boundary Policy
* Service Linked Roles
* EC2 Instance Roles

---
* Policies provide authorization
  1. Specification - Defining policies
  2. Enforcement - Evaluating policies


```
{
  "Statement" : [
    {
      "EFFECT" : "Allow / Deny",
      "PRINCIPLE" : "Users / Groups / Roles / Resources like buckets",
      "ACTION" : "what principle can do (create/delete/list/update)",
      "RESOURCE" : "ARN ( Amazon Resource Name )",
      "CONDITION" : {
        "condition" : {
          "key" : "value"
        }
      }
    }]
}
```

```
========ACTIONS========

<! EC2 Action -->
"Action" : "ec2:StartInstances"

<! IAM Action -->
"Action" : "iam:ChangePassword"

<! S3 Action -->
"Action" : "s3:GetObject"

<! Multiple Action -->
"Action" : ["sqs:SendMessage" , "sqs:ReceiveMessage"]

<! Wildcard  -->
"Action" : "iam:*AccessKey*"

```
___
## AWS Organization

* As a part of AWS organization, SCP's can be deployed and are tied to account
---
## Service Control Policies (SCP)

* SCPs are account permission boundries tied to either Root ORG account or Organization Unit or Individual AWS account.
* They don't grant permissions
* They just limit what an account can do..
