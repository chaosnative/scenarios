#### AWS S3 Bucket Failure Chaos

* Litmus makes use of AWS Go SDK to run service level chaos on aws.

* For Example: S3 bucket policy can be disrupted to see the impact of it on our clusters.

* The provided `aws-permission` will help us to run the chaos on the S3 service.

Refer: https://docs.aws.amazon.com/AmazonS3/latest/userguide/using-with-s3-actions.html
