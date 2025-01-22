
---
title: "Tạo IAM Policy cho Lambda Function"
date: "`r Sys.Date()`"
weight: 3
chapter: false
pre: " <b> 2.3 </b> "
---

Trong phần này, chúng ta sẽ tạo IAM Policy để cấp quyền cho Lambda Function thực hiện các thao tác với objects trong S3 bucket.

### Tạo IAM Policy

1. Truy cập vào Lambda Function **resize-image**
   - Chuyển đến tab **Configuration**
   - Chọn mục **Permissions**
   - Click vào role đang được gắn với function
![CreatePolicy](/images/temp/1/16.png?width=90pc)

2. Tại trang IAM Role **resize-image-role-...**
   - Click **Add permissions**
   - Chọn **Create inline policy**
![CreatePolicy](/images/temp/1/17.png?width=90pc)

3. Tại trang **Create policy**
   - Click **Choose a service** và tìm kiếm **S3**
   - Chọn dịch vụ **S3**
![CreatePolicy](/images/temp/1/18.png?width=90pc)

   - Tại ô tìm kiếm, nhập **GetObject**
   - Tích chọn quyền **GetObject** trong nhóm **Read**
![CreatePolicy](/images/temp/1/19.png?width=90pc)

   - Xóa từ khóa tìm kiếm và nhập **DeleteObject**
   - Tích chọn quyền **DeleteObject** trong nhóm **Write**
   - Click **Add ARNs**
![CreatePolicy](/images/temp/1/20.png?width=90pc)

   - Trong hộp thoại **Specify ARNs**
     - Điền **book-image-stores-by-myself** vào trường **Resource bucket name**
     - Nhập **\*** vào trường **Resource object name**
     - Click **Add ARNs**
![CreatePolicy](/images/temp/1/21.png?width=90pc)

   - Click **+ Add more permissions**
   - Chọn lại service **S3**
![CreatePolicy](/images/temp/1/22.png?width=90pc)

   - Tìm và chọn quyền **PutObject** trong nhóm **Write**
   - Click **Add ARNs**
![CreatePolicy](/images/temp/1/23.png?width=90pc)

   - Trong hộp thoại **Specify ARNs**
     - Điền **book-image-resize-stores-by-myself** vào trường **Resource bucket name**
     - Nhập **\*** vào trường **Resource object name**
     - Click **Add ARNs**
   - Click **Next**
![CreatePolicy](/images/temp/1/24.png?width=90pc)

4. Tại trang **Review policy**
   - Đặt tên policy là **LambdaResizeImageS3Policy**
   - Xem lại cấu hình policy và click **Create policy**
![CreatePolicy](/images/temp/1/25.png?width=90pc)

5. Kiểm tra policy vừa được tạo trong danh sách
![CreatePolicy](/images/temp/1/26.png?width=90pc)

Đến đây, chúng ta đã hoàn tất việc cấp quyền cho Lambda Function để thao tác với objects trong S3 bucket. Bước tiếp theo, chúng ta sẽ kiểm tra chức năng của Lambda Function bằng cách upload một file ảnh test.