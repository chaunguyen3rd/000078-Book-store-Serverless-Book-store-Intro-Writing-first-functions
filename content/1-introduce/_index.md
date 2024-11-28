---
title : "Introduction"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 1. </b> "
---
#### Overview

Before starting to write the first Lambda function, let's learn through the concept of Serverless, and Lambda.

#### Serverless

Serverless is a basic concept that refers to a group of services that are fully managed by AWS. When using these services, you will not need to care about basic daily infrastructure administration tasks such as updating security patches, managing device portfolios, managing assets....

There are many services planned into the Serverless cluster on AWS such as serverless databases like Aurora Serverless, Redshift Serverless, serverless compute like AWS Lambda.

#### AWS Lambda

Lambda is a serverless compute service that allows you to run applications without initializing or managing servers. Lambda runs on a highly available infrastructure platform and does all of the compute resource management, including server and operating system maintenance, capacity provisioning, auto-scaling, and logging. . With Lambda, you can develop almost any kind of backend application or service.

You organize your application into **Lambda functions**. Lambda functions run only when needed and are capable of automatically scaling, from a few requests per day to thousands per second. You only pay for the compute time you use — AWS won't charge when your application is not running.

We'll also start our Serverless Journey with a Lambda function that first resizes the image after uploading it to the S3 bucket, saves the edited image to a new S3 bucket, and deletes the old image.