# Serverless Bookstore: Getting Started with AWS Lambda Functions

> Serverless Bookstore: introduction and first Lambda functions.

A hands-on workshop from the [AWS First Cloud Journey](https://github.com/vanhoangkha/aws-first-cloud-journey) series, available in English and Vietnamese.

**Read the workshop online:** https://vanhoangkha.github.io/000078-Book-store-Serverless-Book-store-Intro-Writing-first-functions/

## Overview

Welcome to this comprehensive guide on building serverless applications with AWS. Modern cloud architecture allows developers to create scalable applications without managing traditional server infrastructure. AWS provides a robust ecosystem of serverless technologies, including:

Here's how these components work together in a typical serverless web application:

## Workshop contents

1. Introduction
2. Image Resizing with AWS Lambda
   - Creating a Lambda Function for Image Processing
   - Create S3 bucket
   - Creating an IAM Policy for Lambda Function
   - Testing Lambda Function Operations
3. Writing Data to Amazon DynamoDB
   - Creating a DynamoDB Table
   - Write data by Lambda function
4. Clean up

## Prerequisites

- An AWS account with permissions to create the resources used in the labs
- Basic familiarity with the AWS Management Console
- [Hugo](https://gohugo.io/installation/) (extended edition) if you want to run the site locally

## Run locally

```bash
git clone https://github.com/vanhoangkha/000078-Book-store-Serverless-Book-store-Intro-Writing-first-functions.git
cd 000078-Book-store-Serverless-Book-store-Intro-Writing-first-functions
hugo server
```

Then open http://localhost:1313 in your browser.

## Repository structure

| Path | Purpose |
| --- | --- |
| `content/` | Workshop pages (`*.md` English, `*.vi.md` Vietnamese) |
| `static/` | Images and other static assets |
| `layouts/` | Hugo layout overrides |
| `themes/` | Hugo theme |
| `config.toml` | Site configuration |

## Cost and cleanup

The labs create AWS resources that may incur charges. Complete the **Clean up** chapter when you finish to remove them.

## Contributing

Contributions are welcome. See [CONTRIBUTING.md](CONTRIBUTING.md).

To report a security issue, see [SECURITY.md](SECURITY.md).

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE).
