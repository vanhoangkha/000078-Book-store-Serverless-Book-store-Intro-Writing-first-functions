---
title : "Clean up"
date: 2024-01-01
weight : 4
chapter : false
pre : " <b> 4. </b> "
---

#### 1. DynamoDB Cleanup

#### Delete DynamoDB Table
1. Navigate to the [DynamoDB Console](https://console.aws.amazon.com/dynamodb)
2. In the left navigation pane, select **Tables**
3. Locate and select the **Books** table
4. Click the **Delete** button
5. Type `confirm` in the confirmation field
6. Click **Delete table** to confirm


#### 2. S3 Bucket Cleanup

#### Empty and Delete First Bucket
1. Go to the [S3 Console](https://console.aws.amazon.com/s3)
2. Find the bucket named `book-image-resize-stores-by-myself`
3. Click **Empty**
4. Type `permanently delete` in the confirmation field
5. Click **Empty** to confirm
6. Select the same bucket again
7. Click **Delete**
8. Type `book-image-resize-stores-by-myself` in the confirmation field
9. Click **Delete bucket** to confirm

#### Delete Second Bucket
1. Locate the bucket named `book-image-stores-by-myself`
2. Click **Delete**
3. Type `book-image-stores-by-myself` in the confirmation field
4. Click **Delete bucket** to confirm



#### 3. Lambda Function Cleanup

#### Delete Lambda Functions
1. Access the [Lambda Console](https://console.aws.amazon.com/lambda)
2. Find and select the `book_create` function
3. Click **Actions**
4. Select **Delete**
5. Type `delete` in the confirmation field
6. Click **Delete** to confirm
7. Repeat the same steps for the `resize_image` function



> **Note:** If you plan to continue with Workshop 2 in this series, you may skip the Lambda function deletion step.

#### Next Steps
After completing these cleanup steps, verify in each service console that the resources have been successfully deleted. This helps prevent any unexpected charges on your AWS account.