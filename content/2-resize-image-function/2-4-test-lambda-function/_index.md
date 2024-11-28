---
title : "Test Lambda function operation"
date : "`r Sys.Date()`"
weight : 4
chapter : false
pre : " <b> 2.4 </b> "
---
1. Navigate to S3 bucket: **book-image-stores**
    - Click **Upload**
![S3Bucket](/images/1/28.png?width=90pc)

2. Click **Add files**
![S3Bucket](/images/1/29.png?width=90pc)

3. Select image to upload, then click **Upload**
![S3Bucket](/images/1/30.png?width=90pc)

4. Wait for the Lambda function running, then check whether the image has been deleted
![S3Bucket](/images/1/31.png?width=90pc)
5. Navigate to S3 bucket: **book-image-resize-stores**
    - Click to image file 
![S3Bucket](/images/1/32.png?width=90pc)

6. Click **Object URL** to download image
![S3Bucket](/images/1/33.png?width=90pc)

7. But error occurs - **Access Denied**.
![S3Bucket](/images/1/34.png?width=90pc)

8. To download image, need add policy for bucket to allow public access.
    - Back to bucket, select **Permission**
    - Click **Edit** in Bucket policy
![S3Bucket](/images/1/35.png?width=90pc)
    - Copy the below json data into **Policy**
        ```
        {
            "Version": "2012-10-17",
            "Statement": [
                {
                    "Sid": "PublicReadGetObject",
                    "Effect": "Allow",
                    "Principal": "*",
                    "Action": "s3:GetObject",
                    "Resource": "arn:aws:s3:::book-image-resize-stores/*"
                }
            ]
        }
        ```
    - Click **Save changes**
![S3Bucket](/images/1/36.png?width=90pc)

9. Then, repeat steps 6 and 7 to download image to local to download an image to your device to compare it with the one you've already uploaded. So Lambda resizes function is working properly.