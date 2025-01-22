---
title: "Creating a DynamoDB Table"
date: "2025-01-22"
weight: 1
chapter: false
pre: "<b> 3.1 </b>"
---


Follow these steps to create a new DynamoDB table:

1. Navigate to the [DynamoDB console](https://console.aws.amazon.com/dynamodb) and select **Create table** from the navigation pane.
   ![DynamoDB Console Create Table](/images/temp/1/35.png?width=90pc)

2. Configure the table basics:
   - For **Table name**, enter `Books`
   - For **Partition key**, enter `id` (this will be your primary key)
   ![DynamoDB Table Configuration](/images/temp/1/36.png?width=90pc)

3. Under **Table settings**, select **Customize settings** and configure:
   - **Table class**: Choose `DynamoDB Standard`
   - **Capacity mode**: Select `On-demand` (this provides pay-per-request pricing)
   ![DynamoDB Table Settings](/images/temp/1/37.png?width=90pc)

4. Review your configuration settings. Keep all other options at their default values and select **Create table** to provision your DynamoDB table.
   ![DynamoDB Create Table Review](/images/temp/1/38.png?width=90pc)