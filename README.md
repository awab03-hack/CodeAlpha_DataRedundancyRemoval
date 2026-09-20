# AWS Data Redundancy Removal Project

## Project Overview

This project is a serverless AWS application designed to detect duplicate data and prevent redundant records from being added to a DynamoDB database.

The project uses AWS Lambda with Python to process incoming data and check whether the provided email already exists in the DynamoDB table.

## AWS Services Used

- AWS Lambda
- Amazon DynamoDB
- Amazon CloudWatch

## How It Works

1. A test event containing user information such as email, name, and phone number is sent to the Lambda function.
2. The Lambda function checks the DynamoDB table using the email address.
3. If the email already exists, the function identifies the data as duplicate.
4. If the email does not exist, the function adds the new record to DynamoDB.
5. CloudWatch Logs can be used to monitor the Lambda executions.

## Testing

Two scenarios were tested:

### Unique Data

When new data was submitted, the Lambda function successfully added the record to DynamoDB and returned:

`Unique data added successfully`

### Duplicate Data

When the same email was submitted again, the Lambda function detected the existing record and returned:

`Duplicate data detected`

## Database

The DynamoDB table stores user information using the email attribute as the partition key.

The table was verified through the DynamoDB Explore Items section, where the stored records could be viewed.

## Key Learning

This project provided practical experience with serverless application development using AWS Lambda and DynamoDB, including database operations, duplicate-data validation, testing Lambda functions, and monitoring executions through CloudWatch.

## Project Result

The project successfully demonstrates how AWS Lambda can be integrated with DynamoDB to validate incoming data and reduce duplicate records in a serverless environment.
