# Cloud Trail

#### Keypoints

- **CloudTrail** is a service in the AWS ecosystem that provides an audit trail of actions performed on AWS service API endpoints. It acts as an audit and logging service, capturing both successful requests and failures. CloudTrail logs are delivered by default to an S3 bucket that is specified when enabling a trail. CloudTrail allows you to have visibility into the history of activity within your AWS account or organization, which is crucial for security, compliance, and troubleshooting purposes.
- **Data events** in CloudTrail refer to the logging of specific activities for AWS resources. These events are selectively logged because not all activities are logged to avoid overwhelming the log records with common, repetitive actions. Data events can be enabled for specific resources such as S3 buckets, Lambda functions, or DynamoDB tables. For example, you can enable data events to log actions like putting an item or getting an item in a DynamoDB table or performing operations on an S3 bucket. Data events provide granular visibility into resource-level actions and help in monitoring and auditing specific operations on AWS resources.
