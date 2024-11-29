---
title : "Ghi dữ liệu với Lambda function"
date :  "`r Sys.Date()`" 
weight : 2
chapter : false
pre : " <b> 3.2 </b> "
---
1. Mở bảng điều khiển [AWS Lambda](https://ap-southeast-2.console.aws.amazon.com/lambda/home?region=ap-southeast-2#/discover). 
    - Nhấn vào **Functions**.
    - Nhấn vào **Create function**.
![LambdaConsole](/images/temp/1/39.png?width=90pc)

2. Ở trang **Create function**.
    - Chọn **Author from scratch**.
    - Nhập tên function: **book_create**.
    - Chọn **Python 3.11** cho **Runtime**
    - Nhấn vào **Create function**.
![LambdaConsole](/images/temp/1/40.png?width=90pc)

3. Ở trang **book_create**.
    - Sao chép đoạn code sau vào tab **lambda_function**.
      ```
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

    - Nhấn **Deploy**.
![LambdaConsole](/images/temp/1/41.png?width=90pc)

4. Tiếp theo, thêm những quyền cần thiết để Lambda function kết nối đến được DynamoDB.
    - Nhấn vào tab **Configure**.
    - Nhấn vào **Permissions** ở menu bên trái.
    - Nhấn vào role ứng với function.
  ![LambdaConsole](/images/temp/1/42.png?width=90pc)
    - Nhấn vào **Attach permissions**.
    - Chọn **Attach policies**.
  ![LambdaConsole](/images/temp/1/43.png?width=90pc)
    - Nhập **AmazonDynamoDBFullAccess** ở ô tìm kiếm chính sách.
    - Chọn chính sách **AmazonDynamoDBFullAccess**.
    - Nhấn vào **Add permission**.
  ![LambdaConsole](/images/temp/1/44.png?width=90pc)

5. Tạo một sự kiện để kiểm tra function có hoạt động không. Ở trang **book_create**.
    - Nhấn vào tab **Test**.
    - Nhập tên sự kiện, ví dụ: **test_1**.
    - Nhập dữ liệu sau vào **Event JSON**.
        ```
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
    - Nhấn vào **Save**.
    - Nhấn vào **Test**.
![LambdaConsole](/images/temp/1/45.png?width=90pc)

6. Điều hướng đến cửa sổ **DynamoDB Tables**.
    - Chọn **Books Tables**. 
    - Nhấn vào **Actions**. 
    - Nhấn vào **Update settings**
![LambdaConsole](/images/temp/1/46.png?width=90pc)

7. Nhấn vào **Explore table items**.
![LambdaConsole](/images/temp/1/47.png?width=90pc)

8. Bạn sẽ lấy được toàn bộ dữ liệu từ bảng.
![LambdaConsole](/images/temp/1/48.png?width=90pc)