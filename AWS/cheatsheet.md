
1. **Amazon Web Services**: It is a cloud computing platform provided by Amazon. It offers a wide range of services and features that enable businesses to build and deploy various applications and services in the cloud.
2. **AWS Account**: Acts as container for AWS resources
     - **Amazon Resournce Name**: arn:partition:service:region:account-id:resource-id
3. **VPC**: Virtual Private datacenter owned by AWS - Region Scope - It enables users to deploy and manage their AWS resources securely within their own defined network boundaries.
4. **Subnets**: Contiguous range of IP addresses in a VPC - AZ Scope - It is used to partition a VPC into smaller networks
5. **VPCPeering**:  Used to establish connectivity between two or more VPC networks. VPC peering allows for the exchange of traffic between the connected VPCs, enabling resources within these VPCs to communicate with each other securely and efficiently. It has limitations in terms of scalability.
     - Modifying the route tables is necessary for a VPC peering connection to enable bidirectional traffic flow between the connected VPCs
6. **TransitGateway(TGW)**: Allows you to connect multiple networks, including VPCs and on-premises networks, and it can scale to handle a higher number of overall networks.
7. **DirectConnect(DX)**: Direct Connect is a region scoped solution, allows on-premises network connectivity to AWS within a specific region.
8. **VirtualPrivateGateway(VGW)**: Virtual Private Gateway is a global solution that can be used to connect on-premises networks to any AWS region.
9. **AWS PrivateLink**: AWS PrivateLink establishes secure connectivity between VPCs and AWS services, preventing exposure of traffic to the internet.
   - PrivateLink essentially provides access to the resources hosted in other VPC or other AWS accounts within the same subnet as the requester. This eliminates the need to use any NAT gateway, IGW, public IP address, or VPN. Therefore, it provides better control over your services, which are reachable via a client VPC
   - AWS PrivateLink enables private connectivity between the Service Provider and Service Consumer using AWS infrastructure to exchange data without going over the public internet. To achieve this, the Service Provider creates an Endpoint Service in a private subnet.
   - You can access AWS services from a VPC using the **Gateway VPC endpoint** and **Interface VPC endpoint**. Gateway endpoints do not support PrivateLink but allow for connection to Amazon S3 and DynamoDB without the need for an IGW or NAT device in your VPC. For other AWS services, an interface VPC endpoint can be created to establish a connection to services through AWS PrivateLink.
10. **AWS Fargate**: Serverless Compute Engine provided by AWS - Used to run containers without managing underlying infrastructure

![image](https://github.com/cskarthik22/Notes/assets/38231831/e13f5b3b-d4aa-4cfe-bf57-2840c242c8cb)

![image](https://github.com/cskarthik22/Notes/assets/38231831/102e1654-2879-4f15-a41a-4396ad3d4580)
