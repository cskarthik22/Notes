## More Advance Concepts

* IAM Roles
* IAM Policies 
  1. Trust policy
  2. Permission Policy
  3. Identity Policy - Controls what that identity can access.
  4. Resource Policy - Controls who can access that resource - it has additional attribute in JSON - called Principle.
  5. Boundary Policy
  6. Bucket Policies - Same as resource policies
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
      "ACTION" : "what principle can do",
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
