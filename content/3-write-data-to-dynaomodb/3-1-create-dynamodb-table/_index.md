---
title : "Create DynamoDB table"
date :  "`r Sys.Date()`" 
weight : 1
chapter : false
pre : " <b> 3.1 </b> "
---
1. Open [DynamoDB console](https://us-east-1.console.aws.amazon.com/dynamodbv2/home?region=us-east-1#dashboard), then Click **Create table**.
![DynamoDBConsole](/000078-Book-store-Serverless-Book-store-Intro-Writing-first-functions/images/temp/1/35.png?width=90pc)

2. Enter table name: **Books**.
    - Enter partition key: **id**.
![DynamoDBConsole](/000078-Book-store-Serverless-Book-store-Intro-Writing-first-functions/images/temp/1/36.png?width=90pc)

3. Scroll down to **Table settings** pattern, select **Customize settings**.
    - In **Table class** pattern, select **DynamoDB Standard**.
    - In **Read/write capacity setting** pattern, select **On-demand**.
![DynamoDBConsole](/000078-Book-store-Serverless-Book-store-Intro-Writing-first-functions/images/temp/1/37.png?width=90pc)

4. Scroll down, leave as default and click **Create table**.
![DynamoDBConsole](/000078-Book-store-Serverless-Book-store-Intro-Writing-first-functions/images/temp/1/38.png?width=90pc)

