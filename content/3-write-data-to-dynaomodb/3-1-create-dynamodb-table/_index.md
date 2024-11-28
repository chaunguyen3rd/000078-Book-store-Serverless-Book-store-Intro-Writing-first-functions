---
title : "Create DynamoDB table"
date :  "`r Sys.Date()`" 
weight : 1
chapter : false
pre : " <b> 3.1 </b> "
---
1. Open [DynamoDB console](https://us-east-1.console.aws.amazon.com/dynamodbv2/home?region=us-east-1#dashboard), then Click **Create table** 
![DynamoDBConsole](/images/1/37.png?width=90pc)

2. Enter table name: **Books**
    - Enter parition key: **id**
![DynamoDBConsole](/images/1/38.png?width=90pc)
3. Scroll down to **Table settings** pattern, select **Customize settings**
    - Then **Table class** pattern, select **DynamoDB Standard**
    - Scroll down to **Read/write capacity setting** pattern, select **On-demand**
![DynamoDBConsole](/images/1/39.png?width=90pc)

4. Leave at default with the options below
5. Scroll to the bottom, click **Create table**.
So you have created the **Books** table

