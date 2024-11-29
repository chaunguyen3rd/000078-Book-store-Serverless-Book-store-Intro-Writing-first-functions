---
title : "Create S3 bucket"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 2.2 </b> "
---
In this part, we will create two S3 buckets:
- Bucket **book-image-stores-by-myself**: to store uploaded image.
- Bucket **book-image-resize-stores-by-myself**: to store image after resize.

1. Open [Amazon S3 console](https://s3.console.aws.amazon.com/s3/get-started?region=us-east-1), then click **Create bucket**.
![S3Console](/images/temp/1/8.png?featherlight=false&width=90pc)

2. At **Create bucket** page.
    - Choose **Bucket type**: General purpose.
    - Enter bucket name, **book-image-stores-by-myself**.
    - Choose **ACLs disabled**.
  ![S3Console](/images/temp/1/9.png?featherlight=false&width=90pc)
    - Uncheck access block: **Block all public access**. 
    - Check the box: **I acknowledge that the current settings might result in this bucket and the objects within becoming public**.
  ![S3Console](/images/temp/1/10.png?featherlight=false&width=90pc)

3. Click **Create bucket**.
![S3Console](/images/temp/1/11.png?featherlight=false&width=90pc)

4. To create bucket - **book-image-resize-stores-by-myself**, repeat steps 1 to 5.

5. At **resize-image** page. We add the trigger.
    - Click **Add Trigger**.
![S3Console](/images/temp/1/12.png?featherlight=false&width=90pc)

6. Enter **S3** and select **S3** service.
![S3Console](/images/temp/1/13.png?featherlight=false&width=90pc)

7. At **At trigger** page.
    - Select bucket **book-image-stores-by-myself** that trigger lambda.
    - Select **All object create events** for **Event type**.
    - Check the box - **I acknowledge that using....** as shown below.
    - Click **Add**.
![S3Console](/images/temp/1/14.png?featherlight=false&width=90pc)

8. Check result after add trigger for Lambda function.
![S3Console](/images/temp/1/15.png?featherlight=false&width=90pc)
