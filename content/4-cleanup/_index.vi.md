
---
title: "Dọn dẹp tài nguyên"
date: 2024-01-01
weight: 4
chapter: false
pre: " <b> 4. </b> "
---

### 1. Xóa DynamoDB Table

Truy cập [AWS Management Console](https://console.aws.amazon.com) và thực hiện các bước sau:

* Điều hướng đến dịch vụ DynamoDB và truy cập [DynamoDB Console](https://console.aws.amazon.com/dynamodbv2/home)
* Trong thanh điều hướng bên trái, chọn mục **Tables**
* Tìm và chọn bảng **Books** từ danh sách
* Click vào nút **Delete** ở góc trên bên phải
* Trong hộp thoại xác nhận, nhập `confirm` và chọn **Delete table**

### 2. Xóa S3 Buckets

Truy cập [S3 Console](https://console.aws.amazon.com/s3) và thực hiện:

* Tìm bucket có tên **book-image-resize-stores-by-myself**
* Chọn bucket và click nút **Empty**
* Nhập `permanently delete` để xác nhận và chọn **Empty bucket**
* Sau khi bucket trống, chọn **Delete**
* Xác nhận bằng cách nhập tên bucket và chọn **Delete bucket**
* Lặp lại quy trình tương tự với bucket **book-image-stores-by-myself**

### 3. Xóa Lambda Functions

Truy cập [Lambda Console](https://console.aws.amazon.com/lambda) và thực hiện:

* Tìm function **book_create**
* Click vào **Actions** và chọn **Delete**
* Nhập `delete` để xác nhận và chọn **Delete function**
* Lặp lại các bước trên với function **resize_image**

{{% notice note %}}
Nếu bạn dự định tiếp tục với phần 2 của series, bạn có thể bỏ qua việc xóa Lambda functions.
{{% /notice %}}
