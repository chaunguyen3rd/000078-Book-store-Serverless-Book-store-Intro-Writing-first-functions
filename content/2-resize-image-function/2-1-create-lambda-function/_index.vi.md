---
title : "Tạo Lambda function chỉnh ảnh"
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : " <b> 2.1 </b> "
---
1. Mở bảng điều khiển [AWS Lambda](https://ap-southeast-1.console.aws.amazon.com/lambda/home?region=ap-southeast-2#/discover), sau đó chọn **Create function**.
![LambdaConsole](/images/temp/1/1.png?width=90pc)

2. Ở trang **Create function**.
    - Chọn **Author from scratch**.
    - Nhập tên function, ví dụ: **resize-image**.
    - Chọn **Node.js 20.x** cho mục **Runtime**.
    - Để nguyên như mặc định và nhấn nút **Create function**.
![CreateFunction](/images/temp/1/2.png?width=90pc)

3. Tải tệp source code máy của bạn
{{%attachments title="Source code" pattern=".*\.(zip)$"/%}}

4. Ở trang **resize-image**.
    - Ấn nút **Upload from**.
    - Chọn **.zip file**.
![CreateFunction](/images/temp/1/3.png?width=90pc)

5. Ở hộp thoại **Upload a .zip file**.
    - Nhấn nút **Upload** và chọn tệp source code mà bạn đã tải về.
    - Nhấn **Save**.
![CreateFunction](/images/temp/1/4.png?width=90pc)

6. Ở trang **resize-image**.
    - Chọn tab **Configuration**
    - Ấn **Environment variables** ở bên trái.
    - Ấn nút **Edit**.
![CreateFunction](/images/temp/1/5.png?width=90pc)

7. Ở trang **Edit environment variables**.
    - Ấn nút **Add environment variable**, sau đó thêm các biến môi trường sau:
      - **WIDTH**: nhập chiều rộng mới của ảnh, ví dụ 200px.
      - **HEIGHT**: nhập cao mới của ảnh, ví dụ 280px.
      - **DES_BUCKET**: tên của S3 bucket lưu ảnh sau khi thay đổi, chẳng hạn như **book-image-resize-stores-by-myself**.
    - Sau đó ấn **Save**.
![CreateFunction](/images/temp/1/6.png?width=90pc)

Vậy là chúng ta đã hoàn thành xong bước tạo một Lambda function và cấu hình biến môi trường cho nó. Tiếp theo sẽ tạo S3 bucket để lưu ảnh tải lên và ảnh sau khi qua chỉnh sửa.
