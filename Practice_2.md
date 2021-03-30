# Practice Test 2

#### You are developing a function that will be hosted in AWS Lambda. The function will be developed in .Net. Several external libraries are needed for the code to run. Which of the following is the best practice when it comes to working with external dependencies for AWS Lambda?
- Selectively only include the libraries that are required.

#### You have a lambda function that is processed asynchronously. You need a way to check and debug issues if the function fails. How could you accomplish this?
- Assign dead letter queue
- Any Lambda function invoked asynchronously is retried twice before the event is discarded. If the retries fail and you're unsure why, use Dead Letter Queues (DLQ) to direct unprocessed events to an Amazon SQS queue to analyze the failure.

#### You are developing an application that is going to make use of Amazon Kinesis. Due to the high throughput, you decide to have multiple shards for the streams. Which of the following is TRUE when it comes to processing data across multiple shards?
- You cannot guarantee the order of data across multiple shards. It's possible only within a shard.
- Kinesis Data Streams lets you order records and read and replay records in the same order to many Kinesis Data Streams applications. To enable write ordering, Kinesis Data Streams expects you to call the PutRecord API to write serially to a shard while using the sequenceNumberForOrdering parameter. Setting this parameter guarantees strictly increasing of sequence numbers for puts from the same client and to the same partition key.

#### Your company is planning to use the Simple Storage Service to host objects that will be accessed by users. There is a speculation that there would be roughly 6000 GET requests per second. Which of the following could be used to ensure optimal performance?
- Use a CloudFront distribution in front of the S3 bucket :you can use CloudFront to give the objects to the user and cache them at the Edge locations so that the requests on the bucket are reduced.
- Enable S3 Transfer Acceleration: it can speed up content transfers to and from Amazon S3 by as much as 50-500% for long-distance transfer of larger objects.

#### A company has a Cloudformation template that is used to create a huge list of resources. It creates a VPC, subnets, EC2 Instances, Autoscaling Groups, Load Balancers etc. Which of the following should be considered when designing such Cloudformation templates?

A. Ensure to create one entire stack from the template.
B. Look towards breaking the templates into smaller manageable templates.
C. Package the templates together and use the cloudformation deploy command.
D. Package the templates together and use the cloudformation package command.

- Answer - B: As your infrastructure grows, common patterns can emerge in which you declare the same components in each of your templates. You can separate out these common components and create dedicated templates for them. That way, you can mix and match different templates but use nested stacks to create a single, unified stack. Nested stacks are stacks that create other stacks. To create nested stacks, use the AWS::CloudFormation::Stack resource in your template to reference other templates.

#### You are developing a common lambda function that will be used across several development environments such as dev, qa, staging, etc. The lambda function needs to interact with each of these development environments. What is the best way to develop the Lambda function?

A. Create a Lambda function for each environment so that each function can point to its respective environment.
B. Create one Lambda function and use environment variables for each environment to interact.
C. Create one Lambda function and create several versions for each environment.
D. Create one Lambda function and create several ALIAS for each environment.

Answer – B: Environment variables for Lambda functions enable you to dynamically pass settings to your function code and libraries without making changes to your code. Environment variables are key-value pairs that you create and modify as part of your function configuration, using either the AWS Lambda Console, the AWS Lambda CLI or the AWS Lambda SDK. AWS Lambda then makes these key-value pairs available to your Lambda function code using standard APIs supported by the language, like process.env for Node.js functions.