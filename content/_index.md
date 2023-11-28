---
title : "Book Store - Serverless Book store Intro - Writing Lambda functions"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
---
# Book Store - Serverless Book store Intro - Writing Lambda functions

#### Overview

This is a series learning about Serverless in AWS. AWS provides technologies for running code, managing data, and integrating applications, all without managing servers. Those technologies serve users to create applications under the Serverless model. Serverless applications start with AWS Lambda, save data with DynamoDB, receive user requests with API Gateway, host static web with S3/AWS Amplify Console, ....

In this series, you will start the first step to build a book store web application with Serverless services of AWS. This application allows user to register, log in, list all books, and add them to cart. Then, user can check the basket and checkout. For admin user, they can add, delete, edit the book information, manage and process the orders. The below list is all workshops of this series:

- [Introduce Serverless Book Store - Write Lambda Functions](https://000078.awsstudygroup.com)
- [Call API from Front-end](https://000079.awsstudygroup.com)
- [Deploy applications with SAM (Serverless Application Model)](https://000080.awsstudygroup.com)
- [Authentication with AWS Cognito](https://000081.awsstudygroup.com)
- [Set up ACM, Route 53 and CloudFront](https://000082.awsstudygroup.com)
- [Checkout with SQS and SNS](https://000083.awsstudygroup.com)
- [Deploy CI/CD with CodePipeline](https://000084.awsstudygroup.com)
- [Tracing and monitor with XRay and CloudWatch](https://000083.awsstudygroup.com)

The below is the overall architecture of the Book Store application:

![SeverlessExample](/images/serverless-diagram.png)

- Create tables with AWS DynamoDB to save book information and S3 bucket to save book's images.
- Create Lambda function that trigger DynamoDB table and S3 bucket.
- Use AWS SNS to send a notification to admin every time an order is placed.
- Save the orders into a queue by AWS SQS to manage.
- Register, login and authenticate user by AWS Cognito.
- Create, publish APIs with AWS API Gateway.

In the first post of this series, we'll learn the basics of Serverless and practice creating functions with Lambda that are triggered from S3 and write data to a DynamoDB table.

#### Content

 1. [Introduce](1-introduce/)
 2. [Create Lambda function to resize images](2-resize-image-function/)
 3. [Create Lambda function to write data to DynamoDB](3-write-data-to-dynaomodb/)
