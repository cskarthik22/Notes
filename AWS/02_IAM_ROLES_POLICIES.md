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
---
```
{
  "Statement" : [
    {
      "EFFECT" : "effect",
      "PRINCIPLE" : "principle",
      "ACTION" : "action",
      "RESOURCE" : "arn",
      "CONDITION" : {
        "condition" : {
          "key" : "value"
        }
      }
    }]
}
```
___
## AWS Organization

---
## Service Control Policies (SCP)

* SCPs are account permission boundries tied to either Root ORG account or Organization Unit or Individual AWS account.
* They don't grant permissions
* They just limit what an account can do..
