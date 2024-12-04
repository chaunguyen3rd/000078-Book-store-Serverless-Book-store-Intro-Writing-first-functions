---
title : "Kiểm tra hoạt động của Lambda function"
date : "`r Sys.Date()`"
weight : 4
chapter : false
pre : " <b> 2.4 </b> "
---
1. Điều hướng đến S3 bucket: **book-image-stores-by-myself**.
    - Ấn nút **Upload**
![S3Bucket](/000078-Book-store-Serverless-Book-store-Intro-Writing-first-functions/images/temp/1/27.png?width=90pc)

2. Ở trang **Upload**.
    - Ấn nút **Add files**.
    - Chọn tệp và bấm vào **Upload**.
![S3Bucket](/000078-Book-store-Serverless-Book-store-Intro-Writing-first-functions/images/temp/1/28.png?width=90pc)

3. Đợi một lúc để Lambda function chạy, sau đó kiểm tra lại xem ảnh đã được xóa chưa.
![S3Bucket](/000078-Book-store-Serverless-Book-store-Intro-Writing-first-functions/images/temp/1/29.png?width=90pc)

4. Điều hướng đến S3 bucket: **book-image-resize-stores-by-myself**.
    - Ấn vào tệp hình ảnh.
![S3Bucket](/000078-Book-store-Serverless-Book-store-Intro-Writing-first-functions/images/temp/1/30.png?width=90pc)

5. Ấn vào **Object URL** để tải ảnh về.
![S3Bucket](/000078-Book-store-Serverless-Book-store-Intro-Writing-first-functions/images/temp/1/31.png?width=90pc)

6. Nhưng có lỗi xảy ra - **Access Denied**.
![S3Bucket](/000078-Book-store-Serverless-Book-store-Intro-Writing-first-functions/images/temp/1/32.png?width=90pc)

7. Để tải ảnh về, cần thêm chính sách cho bucket để cho phép các truy cập công cộng.
    - Quay về bucket, chọn **Permission**.
    - Ấn nút **Edit** ở chính sách Bucket.
  ![S3Bucket](/000078-Book-store-Serverless-Book-store-Intro-Writing-first-functions/images/temp/1/33.png?width=90pc)
    - Sao chép đoạn dữ liệu json sau vào **Policy**.
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
    - Ấn vào **Save changes**.
  ![S3Bucket](/000078-Book-store-Serverless-Book-store-Intro-Writing-first-functions/images/temp/1/34.png?width=90pc)

8. Sau đó, bạn hãy thực hiện lại 6 và 7 để tải ảnh về máy để so sánh với ảnh mà bạn đã tải lên. Vậy là Lambda resize function đã hoạt động bình thường.





