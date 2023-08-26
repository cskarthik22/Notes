# AWS Kinesis Firehose

#### Keypoints

- Amazon Kinesis Data Firehose is a **fully managed** service for delivering real-time streaming data to destinations such as Amazon Simple Storage Service (Amazon S3), Amazon Redshift, Amazon OpenSearch Service, Amazon OpenSearch Serverless, Splunk, and any custom HTTP endpoint or HTTP endpoints owned by supported third-party service providers, including Datadog, Dynatrace, LogicMonitor, MongoDB, New Relic, Coralogix, and Elastic.
- With Kinesis Data Firehose, you **don't need to write applications** or manage resources. You configure your data producers to send data to Kinesis Data Firehose, and it automatically delivers the data to the destination that you specified. You can also configure Kinesis Data Firehose to transform your data before delivering it.
- Kinesis Data Firehose is the feature of Amazon Kinesis that is designed for many-to-one workloads.It provides the capability to collect data from multiple producers and deliver it to a single destination.
- Data Firehose offers additional features compared to Data Streams, including data
manipulation and transformation, buffer and batch configuration, automatic compression, and
support for various destination options. It allows you to convert data formats, filter or remove
specific elements, and utilize Lambda functions for data transformation

