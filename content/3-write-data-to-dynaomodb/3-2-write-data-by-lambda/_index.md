---
title : "Write data by Lambda function"
date :  "`r Sys.Date()`" 
weight : 2
chapter : false
pre : " <b> 3.2 </b> "
---


#### Creating the Lambda Function

1. Navigate to the [AWS Lambda Console](https://console.aws.amazon.com/lambda/)
   - Select **Functions** from the left navigation
   - Click **Create function**
   ![Lambda Console Navigation](/images/temp/1/39.png?width=90pc)

2. Configure the Function Settings:
   - Select **Author from scratch**
   - Function name: `book_create`
   - Runtime: **Python 3.11**
   - Click **Create function**
   ![Lambda Function Creation](/images/temp/1/40.png?width=90pc)

3. Implement the Function Code:
   - In the **Code** tab, replace the contents with:

   ```python
   import boto3
   import json

   client = boto3.resource('dynamodb')
       
   def lambda_handler(event, context):
       book_item = event["body"]
       error = None
       
       try:
           table = client.Table('Books')
           table.put_item(Item = book_item)
       except Exception as e:
           error = e
           
       if error is None:
           response = {
               'statusCode': 200,
               'body': 'writing to dynamoDB successfully!',
               'headers': {
                   'Content-Type': 'application/json'
               },
           }
       else:
           response = {
               'statusCode': 400,
               'body': 'writing to dynamoDB fail!',
               'headers': {
                   'Content-Type': 'application/json'
               },
           }
   
       return response
   ```

   - Click **Deploy** to save your changes
   ![Lambda Function Code](/images/temp/1/41.png?width=90pc)

#### Configuring Permissions

4. Set up DynamoDB Access:
   - Navigate to the **Configuration** tab
   - Select **Permissions** from the left sidebar
   - Click the execution role link
   ![Lambda Permissions](/images/temp/1/42.png?width=90pc)

5. Add DynamoDB Policy:
   - Click **Attach permissions**
   - Select **Attach policies**
   ![Add Policy](/images/temp/1/43.png?width=90pc)
   - Search for and select **AmazonDynamoDBFullAccess**
   - Click **Add permission**
   ![DynamoDB Policy](/images/temp/1/44.png?width=90pc)

#### Testing the Function

6. Create a Test Event:
   - Go to the **Test** tab
   - Create a new test event named `test_1`
   - Use this sample JSON:

   ```json
   {
     "body": {
         "id": "1",
         "name": "Java",
         "author": "Alex",
         "category": "IT",
         "price": "10.89",
         "description": "This book guide to create Java web basic",
         "image": "https://book-image-resize-store.s3.us-east-1.amazonaws.com/Java.jpg"
     }
   }
   ```

   - Click **Save**, then **Test**
   ![Test Configuration](/images/temp/1/45.png?width=90pc)

#### Verifying Data in DynamoDB

7. Access Your DynamoDB Table:
   - Open the DynamoDB console
   - Select the **Books** table
   - Click **Actions** > **Update settings**
   ![DynamoDB Table Access](/images/temp/1/46.png?width=90pc)

8. View Table Items:
   - Select **Explore table items**
   ![Explore Items](/images/temp/1/47.png?width=90pc)

9. Review the Data:
   - Verify your test data appears in the table
   ![Table Data](/images/temp/1/48.png?width=90pc)
