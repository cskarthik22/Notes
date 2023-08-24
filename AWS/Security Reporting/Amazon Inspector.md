# Amazon Inspector

#### Keypoints
- Amazon Inspector is a service, kind of like guard duty, in that the majority of the time is spent evaluating and remediating findings rather than enabling and configuring the service
- Account Scope (technically region-scoped)
- It is designed to evaluate vulnerabilities for certain resource types within the AWS account, and it focuses specifically on EC2 instances and the elastic container registry repository images. So it's not going to look at running containers in ECS
- So from an EC2 perspective, it's going to look for instances that already have the systems manager agent installed, configured, and with the appropriate permissions. It will continually scan, so it executes at least once a day across all of the resources, and it maintains a vulnerability database where you can actually view all of the different findings for your account and compare them to which rule generated them
- So the first thing it can do is it can look at packages, and for these, it uses CVEs, common vulnerabilities and exposures. CVEs are maintained outside of AWS, and AWS simply pulls in the list of those vulnerabilities and then evaluates running instances or container images against them. The other type of rules that are evaluated are based on network reachability, and this is gonna be for EC2 only, not for ECR,
