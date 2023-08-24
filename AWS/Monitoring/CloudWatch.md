# AWS Cloud Watch

#### Keypoints
- The primary function of AWS CloudWatch is to collect and track metrics from various applications and resources deployed in AWS.
- CloudWatch Logs in AWS is designed to allow users to push log entries into the CloudWatch service, where they are aggregated and persisted in a reliable manner. It provides a region-scoped and fault-tolerant feature that ensures the durability of log data. CloudWatch Logs integrates with various AWS services, allowing you to automatically deliver logs from services like CloudTrail, API Gateway, ECS containers, Lambda functions, RDS or Aurora engines, and more

<img width="763" alt="image" src="https://github.com/cskarthik22/Notes/assets/38231831/66ba61e6-4309-4aa3-a730-b81af2283a98">

### Cloudwatch Logs Subscription Filters
- Only 2 subscription filters allowed per log group
- Cloudwatch logs can be exported to S3 manually, but this can be automated using Kinesis Firehose subscription filter
- CloudWatch Logs supports subscription filters, which enable the delivery of logs to other services such as Kinesis Data Streams, Kinesis Data Firehose, and Lambda functions
<img width="674" alt="image" src="https://github.com/cskarthik22/Notes/assets/38231831/67fb6a09-cf14-4ff2-bd6c-4c112c80d093">

