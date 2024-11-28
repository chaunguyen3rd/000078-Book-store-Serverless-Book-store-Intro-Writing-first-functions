---
title : "Tạo S3 bucket"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 2.2 </b> "
---
Phần này, chúng ta sẽ tạo hai S3 bucket:
- Bucket **book-image-stores**: để lưu ảnh lên
- Bucket **book-image-resize-stores**: để lưu ảnh sau khi thay đổi kích thước

1. Mở bảng điều khiển [Amazon S3](https://s3.console.aws.amazon.com/s3/get-started?region=ap-southeast-2), sau đó chọn **Create bucket**
![S3Console](/images/1/8.png?featherlight=false&width=90pc)

2. General configuration
    - Chọn **Bucket type**: General purpose
    - Nhập tên bucket, **book-image-stores**
    - Chọn **ACLs disabled**
    - Bỏ chọn access block: **Block all public access** 
    - Check the box: **I acknowledge that the current settings might result in this bucket and the objects within becoming public**
    ![S3Console](/images/1/9.png?featherlight=false&width=90pc)

3. Ấn nút **Create bucket**
![S3Console](/images/1/9.png?featherlight=false&width=90pc)

4. Tương tự để tạo bucket **book-image-resize-store**, làm lại các bước từ 1 tới 5.
5. Sau khi tạo xong hai bucket, chúng ta thêm trigger cho lambda function tạo ra trước đó
    - Ấn vào **Add Trigger**
![S3Console](/images/1/11.png?featherlight=false&width=90pc)

6. Nhập **S3** và chọn dịch vụ **S3**
![S3Console](/images/1/12.png?featherlight=false&width=90pc)

7. Chọn bucket để triger lambda, **book-image-stores**
    - Chọn **All object create events** cho mục **Event type**
    - Tích chọn **I acknowledge that using....** như hình
    - Ấn nút **Add**
![S3Console](/images/1/13.png?featherlight=false&width=90pc)

10. Xem kết quả sau đi thêm trigger cho Lambda function
![S3Console](/images/1/14.png?featherlight=false&width=90pc)






