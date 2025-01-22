---
title : "Tạo bảng trong AWS DynamoDB"
date :  "`r Sys.Date()`" 
weight : 1
chapter : false
pre : " <b> 3.1 </b> "
---
1. Mở bảng điều khiển [DynamoDB](https://us-east-1.console.aws.amazon.com/dynamodbv2/home?region=us-east-1#dashboard), sau đó nhấn nút **Create table**.
![DynamoDBConsole](/images/temp/1/35.png?width=90pc)

2. Nhập tên cho bảng: **Books**.
    - Nhập parition key: **id**.
![DynamoDBConsole](/images/temp/1/36.png?width=90pc)

3. Kéo xuống phần **Table settings**, chọn **Customize settings**.
    - Ở phần **Table class**, chọn **DynamoDB Standard**.
    - Ở phần **Read/write capacity setting**, chọn **On-demand**.
![DynamoDBConsole](/images/temp/1/37.png?width=90pc)

4. Kéo xuống, giữ nguyên như mặc định và nhấn nút **Create table**.
![DynamoDBConsole](/images/temp/1/38.png?width=90pc)