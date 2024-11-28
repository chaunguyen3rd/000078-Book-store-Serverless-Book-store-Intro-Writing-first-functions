---
title : "Create Policy for Lambda function"
date : "`r Sys.Date()`"
weight : 3
chapter : false
pre : " <b> 2.3 </b> "
---
In this part, we will create a Policy that grants the Lambda function permission to get, write, and delete objects in the S3 bucket.
1. Navigate to console of created in step 1 Lambda function.
    - In tab **Configuration**, click **Permissions**
    - Click on the role being executed by the function
![CreatePolicy](/images/1/15.png?width=90pc)

2. Click **Add permissions**
    - Select **Attach policies**
![CreatePolicy](/images/1/16.png?width=90pc)

3. Click **Create policy**
![CreatePolicy](/images/1/17.png?width=90pc)

4. Click **Choose a service** and Enter **S3**, then select **S3**
![CreatePolicy](/images/1/18.png?width=90pc)

6. Click **Action**, expand **Read** in **Access level**
    - Check to **GetObject** permission
![CreatePolicy](/images/1/19.png?width=90pc)

7. Then, expand **Write**
    - Check to **DeleteObject** permission
![CreatePolicy](/images/1/20.png?width=90pc)

8. In **Resource**, click **Add ARN** to specify resources.
![CreatePolicy](/images/1/21.png?width=90pc)

9. Enter bucket name: **book-image-shop**
    - Check to **Any** to allow permissions for all objects in the bucket
    - Click **Add**
![CreatePolicy](/images/1/22.png?width=90pc)

10. Click **Add additional permissions**

![CreatePolicy](/images/1/23.png?width=90pc)

11. Repeat steps 4 and 5 and 
    - Then, expand **Write**, check to **PutObject** permission
    - click **Add ARN** to specify resources.
![CreatePolicy](/images/1/24.png?width=90pc)

12. Repeat steps 8 and 9 with bucket name is **book-image-resize-shop**
![CreatePolicy](/images/1/25.png?width=90pc)

13. Click **Next**, Enter policy name, such as: **LambdaResizeImageS3Policy**
    - Review policy information and click **Create policy**
![CreatePolicy](/images/1/26.png?width=90pc)

14. Back to adding policy for Lambda function screen, enter the name of the policy we just created.
    - Check to the policy: **LambdaResizeImageS3Policy**
    - Click **Attach policies**
![CreatePolicy](/images/1/27.png?width=90pc)

We have finished granting the Lambda function read, write, and delete permissions from the S3 bucket. The next step is to test the Lambda function working when uploading an image.