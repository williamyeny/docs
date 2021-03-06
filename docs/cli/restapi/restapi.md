---
title: Overview
description: Use Amplify CLI's simple guided workflow to add REST APIs to cloud-based web and mobile apps.
---

## Set up a REST API with NoSQL database

During the CLI setup, you'll be guided through to create a new Lambda function with a predefined [serverless-express](https://github.com/awslabs/aws-serverless-express) template with routing enabled for your REST API paths with support for CRUD operations to DynamoDB tables (which you can create by following the CLI prompts or use the tables which you've already configured using the `amplify add storage` command).

```bash
amplify add api
```

```console
? Please select from one of the below mentioned services REST
? Provide a friendly name for your resource to be used as a label for this category in the project: myRESTAPI
? Provide a path (e.g., /items) /items
? Choose a Lambda source Create a new Lambda function
? Provide a friendly name for your resource to be used as a label for this category in the project: betatest1d2654ef
? Provide the AWS Lambda function name: betatest1d2654ef
? Choose the function template that you want to use:
❯ CRUD function for Amazon DynamoDB table (Integration with Amazon API Gateway and Amazon DynamoDB)
  Serverless express function (Integration with Amazon API Gateway)
```

In the example above with `/items` path, the following API will be created for you:

1. GET /items/[ID] will return a list containing the item at the [ID]. If the item does not exist then an empty array is returned.
2. GET /items/object/[ID] will return a single item at [ID]. If the item does not exist then an empty object is returned.
3. PUT /items with your item in the request body will create or update the item.
4. POST /items with your item in the request body will create or update the item.
5. DELETE /items/object/[ID] will delete the item.

When you have a sort key, you can append it to the end of the path, for example: `GET /items/object/[ID]/[SORT_KEY_ID]`

## REST endpoint that triggers new Lambda functions
During the CLI setup, you'll be guided through to create a new Lambda function with a predefined [serverless-express](https://github.com/awslabs/aws-serverless-express) template with routing enabled for your REST API paths.

```bash
amplify add api
```

```console
? Please select from one of the below mentioned services REST
? Provide a friendly name for your resource to be used as a label for this category in the project: myRESTAPI
? Provide a path (e.g., /items) /items
? Choose a Lambda source Create a new Lambda function
? Provide a friendly name for your resource to be used as a label for this category in the project: betatest1d2654ef
? Provide the AWS Lambda function name: betatest1d2654ef
? Choose the function template that you want to use:
  CRUD function for Amazon DynamoDB table (Integration with Amazon API Gateway and Amazon DynamoDB)
❯ Serverless express function (Integration with Amazon API Gateway)
```

## REST endpoint that triggers existing Lambda functions
During the CLI setup, you'll be guided through to use your own Lambda functions which you've initialized as a part of your CLI project using the `amplify add function` command. This would allow you to have custom logic in your Lambda function and not use the predefined [serverless-express](https://github.com/awslabs/aws-serverless-express) templates generated by the CLI as in the examples above.

```bash
amplify add api
```

```console
? Please select from one of the below mentioned services REST
? Provide a friendly name for your resource to be used as a label for this category in the project: myRESTAPI
? Provide a path (e.g., /items) /items
? Choose a Lambda source
  Create a new Lambda function
❯ Use a Lambda function already added in the current Amplify project
```
