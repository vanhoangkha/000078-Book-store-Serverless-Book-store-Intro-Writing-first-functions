---
title: "Tạo Lambda Function Xử Lý Ảnh"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: "<b> 2.1 </b>"
---

### Tạo Lambda Function

1. Truy cập [AWS Lambda Console](https://ap-southeast-1.console.aws.amazon.com/lambda/home?region=ap-southeast-2#/discover) và chọn **Create function**.

![Giao diện Lambda Console](/images/temp/1/1.png?width=90pc)

2. Tại trang **Create function**:
   - Chọn **Author from scratch**
   - Đặt tên function (ví dụ: **resize-image**)
   - Chọn **Runtime** là **Node.js 20.x**
   - Giữ các cài đặt khác mặc định và nhấn **Create function**

![Tạo Lambda Function](/images/temp/1/2.png?width=90pc)

### Cấu Hình Source Code

3. Tải source code mẫu:
{{% attachments title="Source code" pattern=".*\.(zip)$" /%}}

4. Trong trang **resize-image**:
   - Chọn **Upload from**
   - Chọn **.zip file**

![Upload Source Code](/images/temp/1/3.png?width=90pc)

5. Trong hộp thoại **Upload a .zip file**:
   - Nhấn **Upload** và chọn file source code đã tải
   - Nhấn **Save** để xác nhận

![Xác nhận Upload](/images/temp/1/4.png?width=90pc)

### Thiết Lập Môi Trường

6. Tại trang function **resize-image**:
   - Chuyển sang tab **Configuration**
   - Chọn **Environment variables** ở menu bên trái
   - Nhấn **Edit**

![Cấu hình Môi trường](/images/temp/1/5.png?width=90pc)

7. Tại trang **Edit environment variables**:
   - Thêm các biến môi trường sau:
     - **WIDTH**: Chiều rộng ảnh mới (ví dụ: 200px)
     - **HEIGHT**: Chiều cao ảnh mới (ví dụ: 280px)
     - **DES_BUCKET**: Tên S3 bucket đích (ví dụ: **book-image-resize-stores-by-myself**)
   - Nhấn **Save** để lưu cấu hình

![Thiết lập Biến Môi trường](/images/temp/1/6.png?width=90pc)

### Bước Tiếp Theo

Sau khi hoàn tất cấu hình Lambda function và các biến môi trường, bước tiếp theo là tạo S3 bucket để lưu trữ ảnh gốc và ảnh đã được xử lý.