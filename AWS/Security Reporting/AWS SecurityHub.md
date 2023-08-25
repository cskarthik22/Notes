# AWS Security HUB

<img width="1043" alt="image" src="https://github.com/cskarthik22/Notes/assets/38231831/d59847e3-ede8-46a0-85b8-593f8065dcff">


#### Keypoints
- This service primarily operates at a region scope and it provides a centralized view of that security posture including alerts, findings, consolidated view from a number of different other security services in AWS, and it prioritizes all of those alerts and findings by severity so that any customer with just a couple of minutes can see what their top priorities might be for improving the overall security of their AWS account
- There are three different standards as far as rules that are evaluated in your AWS account.
  - CIS AWS Foundations Benchmark
  - PCI DSS Benchmark
  - AWS Foundational Security Best Practices

### Usecase
- GuardDuty findings can be delivered to Security Hub, but Security Hub can then forward those directly to the Amazon Detective service which then allows you to figure out root causes using a degree of automation. There are a number of other offerings that ingest findings into Security Hub, Inspector, Macie, SSM Patch Manager, IAM Access Analyzer, Firewall Manager. And from there, you can export a lot of these findings into services like the Audit Manager which generates a PDF report that security auditors could use as a baseline before they start to look at individual controls. And you can export all of the findings into SSM OpsCenter as well which creates individual tickets for the remediation of each of those findings.

- <img width="1022" alt="image" src="https://github.com/cskarthik22/Notes/assets/38231831/ff7a5b73-9742-4565-904c-4a7ab73fdbdd">

- <img width="839" alt="image" src="https://github.com/cskarthik22/Notes/assets/38231831/176d540b-5a66-4c12-86af-79590da1163c">
- <img width="733" alt="image" src="https://github.com/cskarthik22/Notes/assets/38231831/d9633507-3f79-4d1b-8a62-faa04a6aa7d7">



  
