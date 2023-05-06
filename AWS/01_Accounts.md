```
AWS Accounts

1. Every AWS account is by default associated with IAM service and a Root User
2. Its recommended to configure MFA to protect Root User
3. Root User doesn't have any restrictions, it has full control of AWS account & the resources created under it.
4. IAM service acts like a database (one per each AWS account )
5. IAM Service / database contains a collection of
    a) IAM Users
    b) IAM Groups
    c) IAM Roles
6. IAM Service does
    a) Manages Identities ( IAM Users, Groups, Roles )
    b) Authenticates 
    c) Authorize ( Allows/Denies access to AWS resources when IAM policies are attached to users/groups/roles )
7. IAM Policies are just the set of rules.

```
