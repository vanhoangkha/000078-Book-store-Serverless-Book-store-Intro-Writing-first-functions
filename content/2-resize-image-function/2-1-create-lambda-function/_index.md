---
title: "Creating a Lambda Function for Image Processing"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: "<b> 2.1 </b>"
---

#### Creating a Lambda Function

1. Navigate to [AWS Lambda Console](https://ap-southeast-1.console.aws.amazon.com/lambda/home?region=ap-southeast-2#/discover) and select **Create function**.

![Lambda Console Interface](/images/temp/1/1.png?width=90pc)

2. On the **Create function** page:
   - Select **Author from scratch**
   - Name your function (e.g., **resize-image**)
   - Choose **Node.js 20.x** as the **Runtime**
   - Keep other settings at their defaults and click **Create function**

![Creating Lambda Function](/images/temp/1/2.png?width=90pc)

#### Configuring Source Code

3. Download the sample source code:
{{% attachments title="Source code" pattern=".*\.(zip)$" /%}}

4. On the **resize-image** page:
   - Select **Upload from**
   - Choose **.zip file**

![Uploading Source Code](/images/temp/1/3.png?width=90pc)

5. In the **Upload a .zip file** dialog:
   - Click **Upload** and select your downloaded source code file
   - Click **Save** to confirm

![Confirming Upload](/images/temp/1/4.png?width=90pc)

#### Setting Up the Environment

6. On the **resize-image** function page:
   - Switch to the **Configuration** tab
   - Select **Environment variables** from the left menu
   - Click **Edit**

![Configuring Environment](/images/temp/1/5.png?width=90pc)

7. On the **Edit environment variables** page:
   - Add the following environment variables:
     - **WIDTH**: New image width (e.g., 200px)
     - **HEIGHT**: New image height (e.g., 280px)
     - **DES_BUCKET**: Destination S3 bucket name (e.g., **book-image-resize-stores-by-myself**)
   - Click **Save** to apply the configuration

![Setting Environment Variables](/images/temp/1/6.png?width=90pc)

#### Next Steps

After completing the Lambda function configuration and environment variables setup, the next step is to create S3 buckets for storing both original and processed images.