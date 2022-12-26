# 401 lab 18 - serverless-api

## Author: Megan Seibert-Hughes
----
## Problem Domain:
- Create a single resource serverless REST API using a domain model of your choice. Needs to be constructed utilizing AWS cloud services.
----
## Step-through of DynamoDB Table Creation

- Create a new tale in DynamoDB
- Name table "people-table"
- Build a schema for table:
    - Partition key `id` of tpe `string`.
    - Attribute `name` of type `string`
    - Attribute `age` of type `number`
    - Attribute `phone` of type `string`

----
## Step-through of Lamba Function Creation
- Create a new Lambda function
    handleCreate
    handleRead
    handleReadOne
    handleUpdate
    handleDelete

- Build new role for the lambda function
- Add the DynamoDB `AmazonDynamoDBFullAccess` policy to the role
----
## Step-through of API Gateway creation
- Build new AWS API Gateway
- Create new resource
    - call resource name `people`
    - Create new methods
        - method type `post`
            - integration type `Lambda Function`
            - Lambda function `handleCreate`
        - Method type `GET`
            - Integration type `Lambda Function`
            - Lambda function `handleRead`
    - Create new resource for {id}
        - Method type `GET`
            - Integration type `Lambda Function
            - Lambda function `handleReadOne`
        - method type `PUT`
            - Integration type Lambda Function.
            - Lambda function handleUpdate.
        
        - Method type DELETE.
            - Integration type Lambda Function.
            - Lambda function handleDelete.
- Test Functions
----

UML

![uml](./Untitled%20(3).png)