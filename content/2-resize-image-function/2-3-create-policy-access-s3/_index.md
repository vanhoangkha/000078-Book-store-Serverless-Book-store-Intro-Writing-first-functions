---
title: "Creating an IAM Policy for Lambda Function"
date: 2024-01-01
weight: 3
chapter: false
pre: " <b> 2.3 </b> "
---

This section guides you through creating an IAM Policy that grants your Lambda function the necessary permissions to perform get, put, and delete operations on objects in your S3 buckets.

### Configure Lambda Function Permissions

1. Navigate to your Lambda function configuration:
   - Open the **resize-image** function
   - Select the **Configuration** tab
   - Click on **Permissions**
   - Click the execution role name to access IAM
![Lambda Permissions](/images/temp/1/16.png?width=90pc)

2. Create a new inline policy:
   - In the IAM role page, select **Add permissions**
   - Choose **Create inline policy**
![Create Inline Policy](/images/temp/1/17.png?width=90pc)

### Define S3 Permissions

3. Configure source bucket permissions:
   - Select **Choose a service** and search for **S3**
   - Click **S3** to select the service
![Select S3 Service](/images/temp/1/18.png?width=90pc)
   - Search for and select **GetObject** under **Read** actions
![GetObject Permission](/images/temp/1/19.png?width=90pc)
   - Clear the search and add **DeleteObject** under **Write** actions
   - Select **Add ARNs** to specify the resource
![DeleteObject Permission](/images/temp/1/20.png?width=90pc)
   - In the **Specify ARNs** dialog:
     - Set **Resource bucket name** to `book-image-stores-by-myself`
     - Enter `*` for **Resource object name**
     - Confirm with **Add ARNs**
![Source Bucket ARN](/images/temp/1/21.png?width=90pc)

4. Configure destination bucket permissions:
   - Select **+ Add more permissions**
   - Choose **S3** service again
![Add More Permissions](/images/temp/1/22.png?width=90pc)
   - Search for and select **PutObject** under **Write** actions
   - Click **Add ARNs**
![PutObject Permission](/images/temp/1/23.png?width=90pc)
   - In the **Specify ARNs** dialog:
     - Set **Resource bucket name** to `book-image-resize-stores-by-myself`
     - Enter `*` for **Resource object name**
     - Click **Add ARNs**
   - Proceed by clicking **Next**
![Destination Bucket ARN](/images/temp/1/24.png?width=90pc)

### Review and Create Policy

5. Finalize the policy:
   - Name your policy (e.g., `LambdaResizeImageS3Policy`)
   - Review the permissions configuration
   - Click **Create policy** to finish
![Create IAM Policy](/images/temp/1/25.png?width=90pc)

6. Verify the newly created policy in the role's permission list
![Verify Policy](/images/temp/1/26.png?width=90pc)

You have now successfully configured the IAM policy granting your Lambda function the required permissions to interact with both S3 buckets. The next step is to test the Lambda function by uploading an image to verify the complete workflow.