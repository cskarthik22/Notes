# AWS Kinesis Data Stream

#### Keypoints
- Region Scode
- Many to Many work loads
- Data stream created with list of **Shards**
- Kinesis Data Streams is the feature of Amazon Kinesis that is designed to collect and process large streams of data records in real time.
- You can **create data-processing applications**, known as Kinesis Data Streams applications.
- A typical Kinesis Data Streams application reads data from a data stream as data records. These applications can use the Kinesis Client Library, and they can run on Amazon EC2 instances. You can send the processed records to dashboards, use them to generate alerts, dynamically change pricing and advertising strategies, or send data to a variety of other AWS services.
- It acts as a persistence tier, allowing you to store the contents of a data stream for up to 365 days.
- The data in Kinesis Data Streams is replicated across three Availability Zones (AZs), providing durability
similar to other services like Amazon S3.

#### Usecases
- Accelerated log and data feed intake and processing
- Real-time metrics and reporting
- Real-time data analytics
- Complex stream processing
- Real-time aggregation of data followed by loading to data-warehouse or map-reduce cluster
- Multiple Kinesis Data Streams applications can consume data from a stream, so that multiple actions, like archiving and processing, can take place concurrently and independently. For example, two applications can read data from the same stream. The first application calculates running aggregates and updates an Amazon DynamoDB table, and the second application compresses and archives data to a data store like Amazon Simple Storage Service (Amazon S3). The DynamoDB table with running aggregates is then read by a dashboard for up-to-the-minute reports.
