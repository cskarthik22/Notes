Build & Deploy
---

- Code Commit
- Code Build : 
- Code Deploy : Handles Configs + Life cycle hook events
- Code Pipeline

Elastic BeanStalk (PaaS)
---

- User of the service provides the application code & EB handles infrastructure environment to be build around the application
- Used by development teams
- Cloud Formation is Infrastructure as a code.

AWS OpsWork
---

- AWS implementation of managed Chef/puppet setup to autoamte tasks
- Used by Infrastructure teams



- Admin control increases from left to right ( Elastic Beanstalk -> AWSOpswork -> Cloudformation Templates -> Manual setup )
