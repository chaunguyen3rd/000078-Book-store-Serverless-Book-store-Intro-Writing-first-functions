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
![CreatePolicy](/images/temp/1/16.png?width=90pc)

2. At **resize-image-role-...** page.
    - Click **Add permissions**.
    - Select **Create inline policy**.
![CreatePolicy](/images/temp/1/17.png?width=90pc)

1. At **step 1: Specify permissions** page.
    - Click **Choose a service** and Enter **S3**.
    - Select **S3**.
  ![CreatePolicy](/images/temp/1/18.png?width=90pc)
    - Enter **GetObject** at Search box.
    - Choose **GetObject** at **Read** level.
  ![CreatePolicy](/images/temp/1/19.png?width=90pc)
    - Clear Search box and enter **DeleteObject**.
    - Choose **DeleteObject** at **Write** level.
    - Click **Add ARNs**.
  ![CreatePolicy](/images/temp/1/20.png?width=90pc)
    - At **Specify ARNs** modal. 
      - Enter **book-image-stores-by-myself** at **Resource bucket name**.
      - Enter **\*** at **Resource object name**.
      - Click **Add ARNs** button.
  ![CreatePolicy](/images/temp/1/21.png?width=90pc)
    - Click **+ Add more permissions**.
    - Click **Choose a service** and Enter **S3**.
    - Select **S3**.
  ![CreatePolicy](/images/temp/1/22.png?width=90pc)
    - Enter **PutObject**.
    - Choose **PutObject** at **Write** level.
    - Click **Add ARNs**.
  ![CreatePolicy](/images/temp/1/23.png?width=90pc)
    - At **Specify ARNs** modal. 
      - Enter **book-image-resize-stores-by-myself** at **Resource bucket name**.
      - Enter **\*** at **Resource object name**.
      - Click **Add ARNs** button.
    - After modal is closed, click **Next**.
  ![CreatePolicy](/images/temp/1/24.png?width=90pc)

1. Click **Action**, expand **Read** in **Access level**
    - Check to **GetObject** permission
![CreatePolicy](/images/1/19.png?width=90pc)

1. Then, expand **Write**
    - Check to **DeleteObject** permission
![CreatePolicy](/images/1/20.png?width=90pc)

1. In **Resource**, click **Add ARN** to specify resources.
![CreatePolicy](/images/1/21.png?width=90pc)

1. Enter bucket name: **book-image-shop**
    - Check to **Any** to allow permissions for all objects in the bucket
    - Click **Add**
![CreatePolicy](/images/1/22.png?width=90pc)

1.  Click **Add additional permissions**

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