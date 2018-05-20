# aws-compliance-audit
# Version 1.0
AWS Compliance reporting using Config.This Project includes a Lambda function running on Python Boto3 Library.
We get Compliance status of different deployed AWS resources against diferent defined Config rules.AWS run compliance check agaist
deployed resources periodically or on resource change event based on defined config rules.
This Lambda function runs a check against every Resource Type/Resource supported by Config and looks for "NON-COMPLIANT" resources.
Publish results to an SNS Topic and send alert email.
This Project includes a Cloudformation Stack which does following :
1. Creates an IAM Role and Policy for Lambda execution
2. Creates the Lambda function from the .zip file stored in the S3 Bucket
3. Creates a Cloudwatch event to run it on a schedule(cron)

Input:
1. This Cloudormation stack accepts following Parameters:
  1a. pJobSchedule -  A schedule to run the job
  1b. pLambdaSourceFileName - Source .zip file name
  1c. pLambdaSourceS3BucketName - S3 Bucket where the .zip file is stored
  1d. pSNSTopicARN -  ARN of an existing SNS Topic susbcribed to email address

Create an S3 Bucket or use an existing S3 Bucket and upload the .zip and .yaml file.
Create a Cloudformation stack and provide .yaml file path uploaded earlier



