---
title : "Test Lambda function operation"
date : "`r Sys.Date()`"
weight : 4
chapter : false
pre : " <b> 2.4 </b> "
---
1. Navigate to S3 bucket: **book-image-stores-by-myself**.
    - Click **Upload**.
![S3Bucket](/000078-Book-store-Serverless-Book-store-Intro-Writing-first-functions/images/temp/1/27.png?width=90pc)

2. At **Upload** page. 
    - Click **Add files**.
    - Choose files and click **Upload**.
![S3Bucket](/000078-Book-store-Serverless-Book-store-Intro-Writing-first-functions/images/temp/1/28.png?width=90pc)

3. Wait for the Lambda function running, then check whether the image has been deleted.
![S3Bucket](/000078-Book-store-Serverless-Book-store-Intro-Writing-first-functions/images/temp/1/29.png?width=90pc)

4. Navigate to S3 bucket: **book-image-resize-stores-by-myself**.
    - Click to image file.
![S3Bucket](/000078-Book-store-Serverless-Book-store-Intro-Writing-first-functions/images/temp/1/30.png?width=90pc)

5. Click **Object URL** to download image.
![S3Bucket](/000078-Book-store-Serverless-Book-store-Intro-Writing-first-functions/images/temp/1/31.png?width=90pc)

6. But error occurs - **Access Denied**.
![S3Bucket](/000078-Book-store-Serverless-Book-store-Intro-Writing-first-functions/images/temp/1/32.png?width=90pc)

7. To download image, need add policy for bucket to allow public access.
    - Back to bucket, select **Permission**.
    - Click **Edit** in Bucket policy.
  ![S3Bucket](/000078-Book-store-Serverless-Book-store-Intro-Writing-first-functions/images/temp/1/33.png?width=90pc)
    - Copy the below json data into **Policy**.
        ```
        {
            "Version": "2012-10-17",
            "Statement": [
                {
                    "Sid": "PublicReadGetObject",
                    "Effect": "Allow",
                    "Principal": "*",
                    "Action": "s3:GetObject",
                    "Resource": "arn:aws:s3:::book-image-resize-stores-by-myself/*"
                }
            ]
        }
        ```
    - Click **Save changes**.
  ![S3Bucket](/000078-Book-store-Serverless-Book-store-Intro-Writing-first-functions/images/temp/1/34.png?width=90pc)

8. Then, repeat steps 4 and 5 to download image to local to download an image to your device to compare it with the one you've already uploaded. So Lambda resizes function is working properly.