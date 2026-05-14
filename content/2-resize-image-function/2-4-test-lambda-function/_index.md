---
title: "Testing Lambda Function Operations"
date: 2024-01-01
weight: 4
chapter: false
pre: " <b> 2.4 </b> "
---

1. Access your target S3 bucket named **book-image-stores-by-myself**
    - Click the **Upload** button to begin the file upload process
![S3 Bucket Interface](/images/temp/1/27.png?width=90pc)

1. On the **Upload** interface 
    - Select **Add files** to choose your images
    - After selection, click **Upload** to initiate the transfer
![Upload Interface](/images/temp/1/28.png?width=90pc)

1. Monitor the Lambda function execution and verify image processing completion
![Processing Status](/images/temp/1/29.png?width=90pc)

1. Navigate to your destination S3 bucket: **book-image-resize-stores-by-myself**
    - Locate and click on the processed image file
![Destination Bucket](/images/temp/1/30.png?width=90pc)

1. Access the **Object URL** to retrieve your processed image
![Object URL Location](/images/temp/1/31.png?width=90pc)

1. Note: You may encounter an **Access Denied** error at this stage
![Access Denied Error](/images/temp/1/32.png?width=90pc)

1. To enable public image access, configure the bucket policy:
    - Return to the bucket settings and select **Permissions**
    - Locate and click **Edit** in the Bucket policy section
![Bucket Permissions](/images/temp/1/33.png?width=90pc)
    - Insert the following JSON policy:
        ```json
        {
            "Version": "2012-10-17",
            "Statement": [
                {
                    "Sid": "PublicReadGetObject",
                    "Effect": "Allow",
                    "Principal": "*",
                    "Action": "s3:GetObject",
                    "Resource": "arn:aws:s3:::book-image-resize-stores-by-myself/*"
                }
            ]
        }
        ```
    - Confirm by clicking **Save changes**
![Policy Configuration](/images/temp/1/34.png?width=90pc)

1. After policy configuration, repeat steps 4 and 5 to download the processed image. Compare it with your original upload to verify that the Lambda resize function has performed correctly.