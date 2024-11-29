---
title : "Clean up"
date :  "`r Sys.Date()`" 
weight : 4
chapter : false
pre : " <b> 4. </b> "
---
1. Delete DynamoDB table.
- Open [DynamoDB console](https://ap-southeast-2.console.aws.amazon.com/dynamodbv2/home?region=ap-southeast-2#dashboard).
- Select **Tables** on the left menu.
- Select **Books** table.
- Click **Delete**.
- Enter **confirm** and click **Delete table**.

2. Delete S3 bucket.
- Open [S3 console](https://s3.console.aws.amazon.com/s3/buckets?region=ap-southeast-2).
- Select **book-image-resize-stores-by-myself** bucket.
- Click **Empty**.
- Enter **permanently delete** and click **Empty**.
- Select **book-image-resize-stores-by-myself** bucket.
- Click **Delete**.
- Enter **book-image-resize-stores-by-myself** and click **Delete bucket**.
- Select **book-image-stores-by-myself** bucket.
- Click **Delete**.
- Enter **book-image-store** and click **Delete bucket**.

3. Delete Lambda function.
- Open [AWS Lambda console](https://ap-southeast-2.console.aws.amazon.com/lambda/home?region=ap-southeast-2#/functions).
- Select **book_create** function.
- Click **Actions**.
- Select **Delete**.
- Enter **delete** and click **Delete**.
- Similar to **resize_image** function.
{{% notice note %}}
If you continue with workshop 2 of the series, you can skip the step of deleting the Lambda function.
{{% /notice %}}