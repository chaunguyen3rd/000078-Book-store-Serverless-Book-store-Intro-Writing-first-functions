---
title : "Tạo S3 bucket"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 2.2 </b> "
---
Phần này, chúng ta sẽ tạo hai S3 bucket:
- Bucket **book-image-stores-by-myself**: để lưu ảnh lên.
- Bucket **book-image-resize-stores-by-myself**: để lưu ảnh sau khi thay đổi kích thước.

1. Mở bảng điều khiển [Amazon S3](https://s3.console.aws.amazon.com/s3/get-started?region=ap-southeast-2), sau đó chọn **Create bucket**.
![S3Console](/images/temp/1/8.png?featherlight=false&width=90pc)

2. Ở trang **Create bucket**.
    - Chọn **Bucket type**: General purpose.
    - Nhập tên bucket, **book-image-stores-by-myself**.
    - Chọn **ACLs disabled**
  ![S3Console](/images/temp/1/9.png?featherlight=false&width=90pc)
    - Bỏ chọn access block: **Block all public access**.
    - Check vào hộp: **I acknowledge that the current settings might result in this bucket and the objects within becoming public**
  ![S3Console](/images/temp/1/10.png?featherlight=false&width=90pc)

3. Ấn nút **Create bucket**.
![S3Console](/images/temp/1/11.png?featherlight=false&width=90pc)

4. Tương tự để tạo bucket **book-image-resize-stores-by-myself**, làm lại các bước từ 1 tới 5.

5. Ở trang **resize-image**, chúng ta thêm trigger.
    - Ấn vào **Add Trigger**.
![S3Console](/images/temp/1/12.png?featherlight=false&width=90pc)

6. Nhập **S3** và chọn dịch vụ **S3**.
![S3Console](/images/temp/1/13.png?featherlight=false&width=90pc)

7. Ở trang **At trigger**.
    - Chọn bucket **book-image-stores-by-myself** để trigger lambda.
    - Chọn **All object create events** cho mục **Event type**.
    - Tích chọn **I acknowledge that using....** như hình bên dưới.
    - Ấn nút **Add**.
![S3Console](/images/temp/1/14.png?featherlight=false&width=90pc)

10. Xem kết quả sau khi thêm trigger cho Lambda function.
![S3Console](/images/temp/1/15.png?featherlight=false&width=90pc)






