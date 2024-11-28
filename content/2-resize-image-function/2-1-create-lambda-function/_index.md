---
title : "Create resize image Lambda function"
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : " <b> 2.1 </b> "
---
1. Open [AWS Lambda console](https://ap-southeast-2.console.aws.amazon.com/lambda/home?region=ap-southeast-2#/discover), then click **Create function** button 
![LambdaConsole](/images/1/1.png?width=90pc)

2. Enter function name, such as: **resize-image**
    - Choose **Node.js 16.x** for **Runtime**
    - Click **Create function** button
![CreateFunction](/images/1/2.png?width=90pc)

3. Download source code file to your device
{{%attachments title="Source code" pattern=".*\.(zip)$"/%}}

4. Click **Upload from** button
    - Choose **.zip file**
![CreateFunction](/images/1/3.png?width=90pc)

5. Click **Upload** button
    - Then select the downloaded source code file
    - Click **Save**
![CreateFunction](/images/1/4.png?width=90pc)
![CreateFunction](/images/1/5.png?width=90pc)
6. Next, add environment variables to adjust the width and height of the image
    - Click **Configuration** tab
    - Click **Environment variables** on the left menu
    - Click **Edit**
![CreateFunction](/images/1/6.png?width=90pc)

7. Click **Add environment variable**, then add the following environment variables:
    - **WIDTH**: enter the new width of the photo, such as 200px.
    - **HEIGHT**: enter the new hight of the photo, such as 280px.
    - **DES_BUCKET**: S3 bucket name to store the changed image, such as: **book-image-resize-stores**.

Then, click **Save**
![CreateFunction](/images/1/7.png?width=90pc)

So we have completed the step of creating a Lambda function and configuring the environment variables for it. Next step, we will create an S3 bucket to store uploaded and edited images.
