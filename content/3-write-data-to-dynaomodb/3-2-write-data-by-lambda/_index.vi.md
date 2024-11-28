---
title : "Ghi dữ liệu với Lambda function"
date :  "`r Sys.Date()`" 
weight : 2
chapter : false
pre : " <b> 3.2 </b> "
---
1. Mở bảng điều khiển [AWS Lambda](https://ap-southeast-2.console.aws.amazon.com/lambda/home?region=ap-southeast-2#/discover), sau đó nhấn nút **Create function** 
![LambdaConsole](/images/1/40.png?width=90pc)

3. Nhập tên cho function: **book_create**
    - Chọn **Python 3.11** cho mục1 **Runtime**
    - Ấn nút **Create function**
![LambdaConsole](/images/1/41.png?width=90pc)

4. Sao chép đoạn code dưới đây vào tab **lambda_function**
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
    - Ấn nút **Deploy**
![LambdaConsole](/images/1/42.png?width=90pc)

5. Tiếp theo, thêm quyền truy cập cho Lambda vào DynamoDB
    - Ấn sang tab **Configure**
    - Chọn mục **Permissions** phía bên trái
    - Ấn vào role mà function đang thực hiện
![LambdaConsole](/images/1/43.png?width=90pc)

    - Ấn nút **Attach permissions**
    - Chọn mục **Attach policies**
![LambdaConsole](/images/1/44.png?width=90pc)

    - Nhập **dynamoDB** để tìm policy thích hợp.
    - Tích chọn policy: **AmazonDynamoDBFullAccess**
    - Ấn nút **Add permision**
![LambdaConsole](/images/1/45.png?width=90pc)

6. Tạo sự kiện để kiểm tra hoạt động của function
    - Ấn sang tab **Test**
    - Nhập tên cho sự kiện, ví dụ: **test_1**
    - Nhập đoạn dữ liệu sau vào **Event JSON**
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
    - Ấn nút **Save**
    - Ấn nút **Test**
![LambdaConsole](/images/1/46.png?width=90pc)

7. Điều hướng đến bảng điều khiển **DynamoDB Tables**
    - Chọn **Books Tables** 
    - Click **Actions** sau đó chọn **Update settings**
![LambdaConsole](/images/1/47.png?width=90pc)
8. Click **Explore table items**
![LambdaConsole](/images/1/48.png?width=90pc)
8. Bạn sẽ nhận được tất cả các dữ liệu của bảng.
![LambdaConsole](/images/1/49.png?width=90pc)
