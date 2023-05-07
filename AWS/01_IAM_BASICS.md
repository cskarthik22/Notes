```
AWS Accounts

1. Every AWS account is by default associated with IAM service and a Root User
2. Its recommended to configure MFA to protect Root User
3. Root User doesn't have any restrictions, it has full control of AWS account & the resources created under it.
4. IAM service acts like a database (one per each AWS account )
5. IAM Service / database contains a collection of
    a) IAM Users ( Maximum of 5000 Users hard limit per AWS Account)
    b) IAM Groups ( User can be part of atmost 10 groups - hard limits )
    c) IAM Roles 
6. IAM Service does
    a) Manages Identities ( IAM Users, Groups, Roles )
    b) Authenticates 
    c) Authorize ( Allows/Denies access to AWS resources when IAM policies are attached to users/groups/roles )
7. IAM Policies are just the set of rules.


**********************************************************************************

1. NO COST
2. Global Service & Reslient
3. No Direct control on external accounts or users
4. Supports Indentity Federation & MFA

            AWS CONSOLE     |     AWS CLI
==================================================================================
Login       IAM USERNAME    |     ACCESS_KEY_ID
                &           |           &
            IAM Password    |     SECRET_ACCESS_KEY
            
5. Can created maximum of 0,1,2 Access Keys per identity ( IAM USers )
6. ***NOTE**** IAM Roles doesnt have access keys

```

** Single Princicple  - Use IAM Users
** Multiple or Un-known number of Identities  - Use IAM roles.
