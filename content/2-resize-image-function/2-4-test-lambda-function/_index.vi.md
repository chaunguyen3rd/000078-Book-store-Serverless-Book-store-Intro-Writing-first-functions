---
title : "Kiểm tra hoạt động"
date : "`r Sys.Date()`"
weight : 4
chapter : false
pre : " <b> 2.4 </b> "
---
1. Điều hướng đến S3 bucket: **book-image-store**
- Ấn nút **Upload**
![S3Bucket](/images/1/28.png?width=90pc)

2. Ấn nút **Add files**
![S3Bucket](/images/1/29.png?width=90pc)

3. Chọn ảnh mà bạn muốn tải lên, sau đó ấn **Upload**
![S3Bucket](/images/1/30.png?width=90pc)
4. Đợi một lúc để Lambda function chạy, sau đó kiểm tra lại xem bucket còn ảnh không
![S3Bucket](/images/1/31.png?width=90pc)

6. Điều hướng sang bucket - **book-image-resize-store**
    - Ấn vào tệp ảnh
![S3Bucket](/images/1/32.png?width=90pc)

7. Ấn vào **Object URL** để tải ảnh về
![S3Bucket](/images/1/33.png?width=90pc)

8. Nhưng bạn sẽ gặp lỗi **access Denied**.
![S3Bucket](/images/1/34.png?width=90pc)
9. Để tải được ảnh, bạn cần thêm policy cho bucket để cho phép truy cập public.
    - Quay lại bucket, chọn mục **Permission**
    - Ấn nút **Edit** tại mục **Bucket policy**
![S3Bucket](/images/1/35.png?width=90pc)

    - Sao chép đoạn json dưới đây mục **Policy**
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
    - Ấn nút **Save changes**
![S3Bucket](/images/1/36.png?width=90pc)

10. Sau đó, bạn hãy thực hiện lại 6 và 7 để tải ảnh về máy để so sánh với ảnh mà bạn đã tải lên. Vậy là Lambda resize function đã hoạt động bình thường.





