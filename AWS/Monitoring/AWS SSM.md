# AWS Systems Manager

#### Keypoints
- Simple Systems Manager (SSM) in AWS is a collection of individual tools that can be used to manage different aspects of your AWS account and resources (Ranging from ticketing systems to OS patching features). It applies to both EC2 instances running discrete operating systems and hybrid environments with on-prem resources (if they meet certain prerequisites).
- SSM is region-scoped and offers five categories of features: operations management, application management, change management, node management, and shared resources.
- And if you are going to manage OS-based resources, you do have to install and configure an SSM agent, as well as providing connectivity and permissions.
- SSM Agent must be able to access Systems Manager Service API endpoint via IGW or NAT GW or VPC Interface Endpoint. Once that Network connectivity gets established, agent will hold that TCP port OPEN and issue a long poll connection against the SSM Service API looking for work, so when you initiate tasks performed almost instantianously.
- SSM can utilize S3 buckets in a specifc regions for certain tasks
- There are five different categories of features within SSM and each of them have at least one tool that can be used by customers.
-   - **Operation Management** ( e.g: Help Desk System ): Incident Manager, SSM Explorer, OpsCenter (which allows you to create tickets called OpsItems), CloudWatch & Trusted Advisor Dashboards, Personal Health Dashbaords
    - **Application Management**: ( Application Manager, AppConfig, Parameter Store )
    - **Change Management** : ( Change Manager, Automation, Change Calender, Maintainence Windows)
    - **Node Management** ( e.g: OS based resources ): Node Management features are designed around individual OS-based resources and include various capabilities for managing and executing commands on those resources, such as Fleet Manager, Compliance, Inventory, Session Manager, State Manager,Patch Manager, Distributor,Hybrid Activations, SSM Run Command, and more.
    - **Shared Resources** ( e.g: Parameters store and access else where in ohter aws services ): SSM Documents
- **SSM Run Command** in AWS Systems Manager allows users to execute commands on EC2 instances and compile the results. It provides a way to remotely manage and execute commands on multiple instances simultaneously, making it convenient for tasks such as collecting information or executing scripts on a fleet of instances.
 
<img width="600" alt="image" src="https://github.com/cskarthik22/Notes/assets/38231831/b9331f30-64be-4e3c-8a73-c191a1c47d27">



