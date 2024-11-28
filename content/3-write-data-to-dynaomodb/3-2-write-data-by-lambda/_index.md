---
title : "Write data by Lambda function"
date :  "`r Sys.Date()`" 
weight : 2
chapter : false
pre : " <b> 3.2 </b> "
---
In this step, we create Lambda function to write data to created DynamoDB table.

1. Open [AWS Lambda console](https://us-east-1.console.aws.amazon.com/lambda/home?region=us-east-1#/discover), then Click **Create function**
![LambdaConsole](/images/1/40.png?width=90pc)

3. Enter function name: **book_create**
    - Select **Python 3.9** for **Runtime**
    - Click **Create function**
![LambdaConsole](/images/1/41.png?width=90pc)

4. Copy the below code into tab **lambda_function**
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

    - Click **Deploy**
![LambdaConsole](/images/1/42.png?width=90pc)

5. Next, add additional permissions for Lambda access to DynamoDB
    - Click to tab **Configure**
    - Click **Permissions** on the left menu
    - Click to role the function executing
![LambdaConsole](/images/1/43.png?width=90pc)

    - Click **Attach permissions**
    - Select **Attach policies**
![LambdaConsole](/images/1/44.png?width=90pc)

    - Enter **dynamoDB** to search policy.
    - Check to policy: **AmazonDynamoDBFullAccess**
    - Click **Add permision**
![LambdaConsole](/images/1/45.png?width=90pc)

6. Create a event to test function operation
    - Click to tab **Test**
    - Enter event name, such as: **test_1**
    - Enter the below data into **Event JSON**
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
    - Click **Save**
    - Click **Test**
![LambdaConsole](/images/1/46.png?width=90pc)

7. Navigate to **DynamoDB Tables** console
    - Choose **Books Tables** 
    - Then click **Actions** then **Update settings**
![LambdaConsole](/images/1/47.png?width=90pc)
8. Click **Explore table items**
![LambdaConsole](/images/1/48.png?width=90pc)
8. You will get all the data from the table.
![LambdaConsole](/images/1/49.png?width=90pc)