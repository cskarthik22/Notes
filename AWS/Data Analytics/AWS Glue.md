# AWS Glue

#### Keypoints
- Serverless ETL ( Extract, Transform, Load)
- The AWS Glue service plays a crucial role in a data analytics pipeline by providing data cataloging and schema creation capabilities. Glue helps users understand the location of their data and facilitates data querying through catalogs. It uses a Data Crawler feature to scan various parts of the AWS ecosystem, including S3, to discover new data and create schemas for better data understanding and querying. Glue integrates tightly with AWS Athena, allowing seamless interaction between the two services. Glue's data catalog can be utilized by other services, such as Amazon Redshift, for further data processing and analysis. In summary, AWS Glue enables efficient data cataloging and schema creation, making it easier to extract insights from the data in an analytics pipeline.
- **Note: Datapipeline also used for ETL, but it is not serverless, it uses EC2 instances to help with the transfer of data

```
The purpose of creating a Data crawler in AWS Glue is to create a data catalog and schema for the data sources.
The Data crawler scans and analyzes the data in the specified data store, such as an S3 bucket, and automatically
creates a catalog with metadata about the data. It examines the data's structure and schema, allowing users to better
understand and query the data. The crawler enables cross-account data extraction, and in this demonstration, it is used
to extract airline flight information from a public dataset provided by AWS. By creating a crawler and configuring it to
crawl the specified data source, a data catalog and schema are generated, facilitating efficient data analysis and querying.
```
