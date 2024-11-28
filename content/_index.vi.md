---
title : "Serverless - Lambda tương tác với S3 và DynamoDB"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
---
# Serverless - Lambda tương tác với S3 và DynamoDB

### Tổng quan

Đây là series về Serverless với AWS Cloud. AWS cung cấp các công nghệ để chạy code, quản lý dữ liệu, và tích hợp các ứng dụng mà không cần quản lý máy chủ. Các công nghệ đó phục vụ cho người dùng tạo các ứng dụng theo mô hình Serverless. Các ứng dụng Serverless bắt đầu với AWS Lambda, lưu dữ liệu với DynamoDB, nhận yêu cầu của người dùng với API Gateway, host static web với S3/AWS Amplify Console,....

Ví dụ về ứng dụng web sử dụng mô hình Serverless với cloud:
![SeverlessExample](/images/Arch-Diagrams_Serverless-Category-Page_WebApp.png?featherlight=false&width=90pc)

Trong bài đầu tiên của series này, chúng ta sẽ tìm hiểu các khái niệm cơ bản về Serverless và thực hành tạo các function với Lambda được trigger từ S3 và ghi dữ liệu vào bảng DynamoDB. 
### Nội dung

 1. [Giới thiệu](1-introduce/)
 2. [Tạo Lambda thay đổi kích thước ảnh](2-resize-image-function/)
 3. [Tạo Lambda ghi dữ liệu vào DynamoDB](3-write-data-to-dynaomodb/)
