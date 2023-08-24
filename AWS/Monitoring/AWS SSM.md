# AWS Systems Manager

#### Keypoints
- The service is really a large collection of management and operational tools which are organized into several categories. Ranging from ticketing systems to OS patching features. SSM can be used to execute commands on EC2 instances or even on premises VMs.
- And if you are going to manage OS-based resources, you do have to install and configure an SSM agent, as well as providing connectivity and permissions.
- SSM Agent must be able to access Systems Manager Service API endpoint via IGW or NAT GW or VPC Interface Endpoint. Once that Network connectivity gets established, agent will hold that TCP port OPEN and issue a long poll connection against the SSM Service API looking for work, so when you initiate tasks performed almost instantianously.
- SSM uses S3 bucket per region tasks
- There are five different categories of features within SSM and each of them have at least one tool that can be used by customers.
-   - **Operation Management** ( e.g: Help Desk System ): Incident Manager, SSM Explorer, OpsCenter (which allows you to create tickets called OpsItems), CloudWatch & Trusted Advisor Dashboards, Personal Health Dashbaords
    - **Application Management**: ( Application Manager, AppConfig, Parameter Store )
    - **Change Management** : ( Change Manager, Automation, Change Calender, Maintainence Windows)
    - **Node Management** ( e.g: OS based resources ): Fleet Manager, Compliance, Inventory, Session Manager, Runcommand, State Manager,Patch Manager, Distributor
    - **Shared Resources** ( e.g: Parameters store and access else where in ohter aws services ): SSM Documents
 
<img width="600" alt="image" src="https://github.com/cskarthik22/Notes/assets/38231831/b9331f30-64be-4e3c-8a73-c191a1c47d27">



