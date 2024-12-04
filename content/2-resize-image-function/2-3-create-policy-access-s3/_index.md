---
title : "Create Policy for Lambda function"
date : "`r Sys.Date()`"
weight : 3
chapter : false
pre : " <b> 2.3 </b> "
---
In this part, we will create a Policy that grants the Lambda function permission to get, write, and delete objects in the S3 bucket.

1. At **resize-image** page.
    - Click tab **Configuration**.
    - Click **Permissions**.
    - Click on the role being executed by the function.
![CreatePolicy](/000078-Book-store-Serverless-Book-store-Intro-Writing-first-functions/images/temp/1/16.png?width=90pc)

2. At **resize-image-role-...** page.
    - Click **Add permissions**.
    - Select **Create inline policy**.
![CreatePolicy](/000078-Book-store-Serverless-Book-store-Intro-Writing-first-functions/images/temp/1/17.png?width=90pc)

3. At **Step 1: Specify permissions** page.
    - Click **Choose a service** and Enter **S3**.
    - Select **S3**.
  ![CreatePolicy](/000078-Book-store-Serverless-Book-store-Intro-Writing-first-functions/images/temp/1/18.png?width=90pc)
    - Enter **GetObject** at Search box.
    - Choose **GetObject** at **Read** level.
  ![CreatePolicy](/000078-Book-store-Serverless-Book-store-Intro-Writing-first-functions/images/temp/1/19.png?width=90pc)
    - Clear Search box and enter **DeleteObject**.
    - Choose **DeleteObject** at **Write** level.
    - Click **Add ARNs**.
  ![CreatePolicy](/000078-Book-store-Serverless-Book-store-Intro-Writing-first-functions/images/temp/1/20.png?width=90pc)
    - At **Specify ARNs** modal. 
      - Enter **book-image-stores-by-myself** at **Resource bucket name**.
      - Enter **\*** at **Resource object name**.
      - Click **Add ARNs** button.
  ![CreatePolicy](/000078-Book-store-Serverless-Book-store-Intro-Writing-first-functions/images/temp/1/21.png?width=90pc)
    - Click **+ Add more permissions**.
    - Click **Choose a service** and Enter **S3**.
    - Select **S3**.
  ![CreatePolicy](/000078-Book-store-Serverless-Book-store-Intro-Writing-first-functions/images/temp/1/22.png?width=90pc)
    - Enter **PutObject**.
    - Choose **PutObject** at **Write** level.
    - Click **Add ARNs**.
  ![CreatePolicy](/000078-Book-store-Serverless-Book-store-Intro-Writing-first-functions/images/temp/1/23.png?width=90pc)
    - At **Specify ARNs** modal. 
      - Enter **book-image-resize-stores-by-myself** at **Resource bucket name**.
      - Enter **\*** at **Resource object name**.
      - Click **Add ARNs** button.
    - After modal is closed, click **Next**.
  ![CreatePolicy](/000078-Book-store-Serverless-Book-store-Intro-Writing-first-functions/images/temp/1/24.png?width=90pc)

4. At **Step 2: Review and create** page.
    - Enter policy name, such as: **LambdaResizeImageS3Policy**.
    - Review policy information and click **Create policy**.
![CreatePolicy](/000078-Book-store-Serverless-Book-store-Intro-Writing-first-functions/images/temp/1/25.png?width=90pc)

5. Check policies just created.
![CreatePolicy](/000078-Book-store-Serverless-Book-store-Intro-Writing-first-functions/images/temp/1/26.png?width=90pc)

We have finished granting the Lambda function read, write, and delete permissions from the S3 bucket. The next step is to test the Lambda function working when uploading an image.