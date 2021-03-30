# Practice Test 2

#### You are developing a function that will be hosted in AWS Lambda. The function will be developed in .Net. Several external libraries are needed for the code to run. Which of the following is the best practice when it comes to working with external dependencies for AWS Lambda?
- Selectively only include the libraries that are required.

#### You have a lambda function that is processed asynchronously. You need a way to check and debug issues if the function fails. How could you accomplish this?
- Assign dead letter queue
- Any Lambda function invoked asynchronously is retried twice before the event is discarded. If the retries fail and you're unsure why, use Dead Letter Queues (DLQ) to direct unprocessed events to an Amazon SQS queue to analyze the failure.