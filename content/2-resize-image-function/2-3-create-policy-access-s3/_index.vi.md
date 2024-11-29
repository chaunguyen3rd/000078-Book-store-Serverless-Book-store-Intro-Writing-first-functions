---
title : "Tạo Policy cho Lambda function"
date : "`r Sys.Date()`"
weight : 3
chapter : false
pre : " <b> 2.3 </b> "
---
Trong bước này chúng ta sẽ tạo Policy cấp quyền cho Lambda function có thể lấy, ghi và xoá object trong S3 bucket.

1. Ở trang **resize-image**.
    - Ấn vào tab **Configuration**.
    - Ấn vào **Permissions**.
    - Ấn vào role mà function đang thực hiện.
![CreatePolicy](/images/temp/1/16.png?width=90pc)

2. Ở trang **resize-image-role-...**.
    - Ấn nút **Add permissions**.
    - Chọn **Create inline policy**.
![CreatePolicy](/images/temp/1/17.png?width=90pc)

3. Ở trang **Step 1: Specify permissions**.
    - Ấn vào **Choose a service** and nhập **S3**.
    - Chọn **S3**.
  ![CreatePolicy](/images/temp/1/18.png?width=90pc)
    - Nhập **GetObject** ở ô Tìm kiếm.
    - Chọn **GetObject** ở cấp **Read**.
  ![CreatePolicy](/images/temp/1/19.png?width=90pc)
    - Xóa ô tìm kiếm và nhập **DeleteObject**.
    - Chọn **DeleteObject** ở cấp **Write**.
    - Ấn vào **Add ARNs**.
  ![CreatePolicy](/images/temp/1/20.png?width=90pc)
    - Ở hộp thoại **Specify ARNs**. 
      - Nhập **book-image-stores-by-myself** ở **Resource bucket name**.
      - Nhập **\*** at **Resource object name**.
      - Ấn vào nút **Add ARNs**.
  ![CreatePolicy](/images/temp/1/21.png?width=90pc)
    - Ấn vào **+ Add more permissions**.
    - Ấn vào **Choose a service** và nhập **S3**.
    - Chọn **S3**.
  ![CreatePolicy](/images/temp/1/22.png?width=90pc)
    - Nhập **PutObject**.
    - Chọn **PutObject** ở cấp **Write**.
    - Ấn vào **Add ARNs**.
  ![CreatePolicy](/images/temp/1/23.png?width=90pc)
    - Ở hộp thoại **Specify ARNs**. 
      - Nhập **book-image-resize-stores-by-myself** ở **Resource bucket name**.
      - Nhập **\*** ở **Resource object name**.
      - Ấn vào nút **Add ARNs**.
    - Sau khi hộp thoại đóng, ấn vào **Next**.
  ![CreatePolicy](/images/temp/1/24.png?width=90pc)

4. Ở trang **Step 2: Review and create**.
    - Nhập tên chính sách, ví dụ: **LambdaResizeImageS3Policy**.
    - Kiểm tra lại thông tin chính sách và ấn vào **Create policy**.
![CreatePolicy](/images/temp/1/25.png?width=90pc)

5. Kiểm tra lại các chính sách đã tạo ra.
![CreatePolicy](/images/temp/1/26.png?width=90pc)

Chúng ta đã hoàn thành cấp quyền đọc, ghi và xoá object trong S3 bucket cho Lambda function. Bước tiếp theo là kiểm tra hoạt động của Lambda fucntion khi tải lên một ảnh.



