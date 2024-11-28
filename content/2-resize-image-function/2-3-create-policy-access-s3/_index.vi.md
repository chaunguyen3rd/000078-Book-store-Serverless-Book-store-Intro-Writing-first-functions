---
title : "Tạo Policy cho Lambda function"
date : "`r Sys.Date()`"
weight : 3
chapter : false
pre : " <b> 2.3 </b> "
---
Trong bước này chúng ta sẽ tạo Policy cấp quyền cho Lambda function có thể lấy, ghi và xoá object trong S3 bucket.
1. Điều hướng tới bảng điều khiển của Lambda bạn đã tạo.
    - Trong tab **Configuration**, chọn mục **Permissions**
    - Ấn vào role mà function đang thực hiện
![CreatePolicy](/images/1/15.png?width=90pc)

2. Ấn nút **Add permissions**
    - Chọn **Attach policies**
![CreatePolicy](/images/1/16.png?width=90pc)

3. Ấn nút **Create policy**
![CreatePolicy](/images/1/17.png?width=90pc)

4. Ấn vào **Choose a service** và nhập **S3**, sau đó chọn **S3**
![CreatePolicy](/images/1/18.png?width=90pc)

6. Ấn vào mục **Action**, mở rộng **Read** trong **Access level**
    - Tích chọn quyền **GetObject**
![CreatePolicy](/images/1/19.png?width=90pc)

7. Sau đó mở rộng mục **Write**
    - Tích chọn quyền **DeleteObject**
![CreatePolicy](/images/1/20.png?width=90pc)

8. Tại mục **Resource**, ấn vào **Add ARN** để chỉ định tài nguyên.
![CreatePolicy](/images/1/21.png?width=90pc)

9. Nhập tên bucket: **book-image-store**
    - Tích vào **Any** cho phép quyền với mọi object trong bucket
    - Ấn **Add**
![CreatePolicy](/images/1/22.png?width=90pc)

10. Ấn **Add additional permissions**
![CreatePolicy](/images/1/23.png?width=90pc)

11. Lặp lại bước 4 và 5
    - Sau đó mở rộng mục **Write**, tích chọn quyền **PutObject**
    - Ấn vào **Add ARN** để chỉ định tài nguyên.
![CreatePolicy](/images/1/24.png?width=90pc)

12. Làm tương tự bước 8, 9.
    - Nhập tên bucket là **book-image-resize-store**
![CreatePolicy](/images/1/25.png?width=90pc)

15. Click **Next**, Nhập tên cho policy, ví dụ: **LambdaResizeImageS3Policy**
    - Xem lại các thông tin và ấn nút **Create policy**
![CreatePolicy](/images/1/26.png?width=90pc)

16. Trở lại màn hình thêm policy cho Lambda function, nhập tên policy chúng ta vừa tạo.
    - Tích chọn policy: **LambdaResizeImageS3Policy**
    - Ấn nút **Attach policies**
![CreatePolicy](/images/1/27.png?width=90pc)

Chúng ta đã hoàn thành cấp quyền đọc, ghi và xoá object trong S3 bucket cho Lambda function. Bước tiếp theo là kiểm tra hoạt động của Lambda fucntion khi tải lên một ảnh.



