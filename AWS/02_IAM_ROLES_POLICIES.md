## More Advance Concepts

* IAM Policies lives with
  1. IAM Users
  2. IAM Groups
  3. IAM Roles - tied with
      1. Trust Policy
      2. Permission Policy
   Note: Identity Policy - Controls what that identity can access.
* Resource Policy - Controls who can access that resource - it has additional attribute in JSON - called Principle.
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

---
## Service Control Policies (SCP)

* SCPs are account permission boundries tied to either Root ORG account or Organization Unit or Individual AWS account.
* They don't grant permissions
* They just limit what an account can do..
