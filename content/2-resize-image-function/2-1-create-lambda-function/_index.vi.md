---
title : "Tạo Lambda function chỉnh ảnh"
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : " <b> 2.1 </b> "
---
1. Mở bảng điều khiển [AWS Lambda](https://ap-southeast-1.console.aws.amazon.com/lambda/home?region=ap-southeast-2#/discover), sau đó chọn **Create function**
![LambdaConsole](/images/1/1.png?width=90pc)

2. Nhập tên function, ví dụ: **resize-image**
    - Chọn **Node.js 16.x** cho mục Runtime
    - Nhấn nút **Create function**
![CreateFunction](/images/1/2.png?width=90pc)

3. Tải tệp source code máy của bạn
{{%attachments title="Source code" pattern=".*\.(zip)$"/%}}

4. Ấn nút **Upload from**
    - Chọn **.zip file**
![CreateFunction](/images/1/3.png?width=90pc)

5. Nhấn nút **Upload**
    - Sau đó chọn tệp source code mà bạn đã tải về
    - Nhấn **Save**
![CreateFunction](/images/1/4.png?width=90pc)
![CreateFunction](/images/1/5.png?width=90pc)

6. Tiếp theo, thêm biến môi trường để chỉnh chiều rộng và cao cho ảnh
    - Chọn tab **Configuration**
    - Ấn **Environment variables** ở bên trái
    - Ấn nút **Edit**
![CreateFunction](/images/1/6.png?width=90pc)

7. Ấn nút **Add environment variable**, sau đó thêm các biến môi trường sau:
    - **WIDTH**: nhập chiều rộng mới của ảnh, ví dụ 200px.
    - **HEIGHT**: nhập cao mới của ảnh, ví dụ 280px.
    - **DES_BUCKET**: tên của S3 bucket lưu ảnh sau khi thay đổi, chẳng hạn như **book-image-resize-stores**.

Sau đó ấn **Save**
![CreateFunction](/images/1/7.png?width=90pc)

Vậy là chúng ta đã hoàn thành xong bước tạo một Lambda function và cấu hình biến môi trường cho nó. Tiếp theo sẽ tạo S3 bucket để lưu ảnh tải lên và ảnh sau khi qua chỉnh sửa.
