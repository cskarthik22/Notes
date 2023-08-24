# CLI Commands

#### S3
- aws s3api create-bucket --bucket $BUCKET --region $REGION
- aws firehose create-delivery-stream
  --region $REGION
  --delivery-stream-name test-delivery-stream
  --delibery-stream-type DirectPut
  --s3-destination-configuration file://s3_config.json
