---
title : "Giới thiệu"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 1. </b> "
---

#### Tổng quan

Trước khi bắt tay vào viết hàm Lambda đầu tiên chúng ta cùng tìm hiểu qua khái niệm về Serverless, và Lambda nhé.

#### Serverless 

Serverless là khái niệm cơ bản để chỉ nhóm các dịch vụ được quản lý hoàn toàn bởi AWS. Khi sử dụng những dịch vụ này thì bạn sẽ không cần quan tâm tới các tác vụ quản trị hạ tầng cơ bản hàng ngày như cập nhật bản vá bảo mật, quản lý danh mục thiết bị, quản lý tài sản....

Có nhiều dịch vụ được quy hoạch vào nhóm Serverless trên AWS ví dụ serverless database như Aurora Serverless, Redshift Serverless, serverless compute như AWS Lambda.

#### AWS Lambda

Lambda là một dịch vụ serverless compute cho phép bạn chạy ứng dụng mà không cần khởi tạo hoặc quản lý máy chủ. Lambda chạy trên nển tảng hạ tầng có tính khả dụng cao và thực hiện tất cả việc quản lý tài nguyên tính toán, bao gồm bảo trì máy chủ và hệ điều hành, cung cấp dung lượng, tự động mở rộng quy mô và ghi log. Với Lambda, bạn có thể phát triển hầu hết mọi loại ứng dụng hoặc dịch vụ phụ trợ.

Bạn tổ chức ứng dụng của mình thành các **Lambda function**. Lambda function chỉ chạy khi cần thiết và có khả năng tự động mở rộng quy mô, từ một vài yêu cầu mỗi ngày đến hàng nghìn mỗi giây. Bạn chỉ phải trả cho thời gian tính toán mà bạn sử dụng — AWS sẽ không tính phí khi ứng dụng của bạn không chạy.

Chúng ta sẽ cũng bắt đầu hành trình Serverless Journey của mình với Lambda function đầu tiên thực hiện thay đổi kích thước ảnh sau khi tải ảnh lên S3 bucket, lưu ảnh sau khi sửa vào một S3 bucket mới và xoá ảnh cũ đi.

