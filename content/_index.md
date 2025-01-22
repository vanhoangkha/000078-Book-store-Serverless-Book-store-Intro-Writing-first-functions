---
title: "Serverless Bookstore: Getting Started with AWS Lambda Functions"
date: "2025-01-22"
weight: 1
chapter: false
---

# Serverless Bookstore: Getting Started with AWS Lambda Functions

## Overview

Welcome to this comprehensive guide on building serverless applications with AWS. Modern cloud architecture allows developers to create scalable applications without managing traditional server infrastructure. AWS provides a robust ecosystem of serverless technologies, including:

- **AWS Lambda** for executing code
- **Amazon DynamoDB** for data persistence
- **Amazon API Gateway** for handling API requests
- **Amazon S3** and **AWS Amplify** for static web hosting

Here's how these components work together in a typical serverless web application:

![Serverless Architecture Diagram](/images/Arch-Diagrams_Serverless-Category-Page_WebApp.png?featherlight=false&width=90pc)

This first guide in our serverless series focuses on fundamental concepts and hands-on practice. You'll learn to create AWS Lambda functions that interact with S3 triggers and store data in DynamoDB tables.

## Table of Contents

1. [Understanding Serverless Architecture](1-introduce/)
   - Core concepts
   - Benefits and use cases
   - AWS serverless services overview

2. [Building an Image Processing Function](2-resize-image-function/)
   - Creating Lambda functions
   - Handling S3 events
   - Image processing with Lambda

3. [Implementing Data Persistence](3-write-data-to-dynaomodb/)
   - DynamoDB basics
   - Writing data from Lambda
   - Best practices for data modeling