# AWS GuardDuty

#### Keypoints

- GuardDuty is a managed threat detection service in AWS. It uses machine learning models to analyze normal behavior in an AWS account and identifies abnormal activities as findings. GuardDuty is designed as a detective control rather than a preventive measure, meaning it cannot stop activity from taking place but can report what has happened. It generates findings of different severities and delivers them to EventBridge by default. GuardDuty can also be configured to deliver findings to an S3 bucket on a per-region basis. Its primary purpose is to identify potential threats and anomalies within your AWS environment for further investigation.
- By providing trusted IP list, GuardDuty ensures that these IP addresses are not evaluated for abnormal behavior, reducing the chances of false positives.
