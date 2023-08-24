# AWS Glue

#### Keypoints
- Serverless ETL ( Extract, Transform, Load)
- **Note: Datapipeline also used for ETL, but it is not serverless, it uses EC2 instances to help with the transfer of data, as well as the ability to issue arbitrary AWS CLI commands in case you need to do any extra work in the middle. And so Data Pipeline can be a little bit more flexible in some ways than the Kinesis offerings. And it does not necessarily require an agent on the producer side to be able to push data into the Data Pipeline to begin with. Data Pipeline supports cross-region activities and cross-accounts

```
The purpose of creating a Data crawler in AWS Glue is to create a data catalog and schema for the data sources.
The Data crawler scans and analyzes the data in the specified data store, such as an S3 bucket, and automatically
creates a catalog with metadata about the data. It examines the data's structure and schema, allowing users to better
understand and query the data. The crawler enables cross-account data extraction, and in this demonstration, it is used
to extract airline flight information from a public dataset provided by AWS. By creating a crawler and configuring it to
crawl the specified data source, a data catalog and schema are generated, facilitating efficient data analysis and querying.
```
