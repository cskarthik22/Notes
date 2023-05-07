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

* When Single Principle / Identity wants to connect to AWS Account -  IAM User / Access Keys can be used
* When Multiple or Un-known number of Principles / Identities (e.g: 5000 users hardlimit ) wants to connect to AWS Account  -  IAM roles are best choice.
* Also when an external identity / identities wants to access an AWS account, then IAM roles are best choice. 
    Example: Microsoft AD account or Web Identities like facebook, twitter..etc.
    
IAM USERS & GROUPS - ATTACHED TO - INLINE OR MANAGED POLICIES
AWS RESOUECES - ATTACHED TO - RESOURCE POLICIES.
IAM ROLES - ATTACHED TO - TRUST POLICIES & PERMISSION POLILIES
