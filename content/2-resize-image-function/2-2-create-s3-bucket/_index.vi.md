
---
title: "Tạo S3 Bucket"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 2.2 </b> "
---

Trong phần này, chúng ta sẽ tạo hai S3 bucket:

* **book-image-stores-by-myself**: Bucket chính để lưu trữ ảnh gốc trước khi xử lý
* **book-image-resize-stores-by-myself**: Bucket đích để lưu trữ ảnh sau khi đã được thay đổi kích thước

### Các bước thực hiện

1. Truy cập vào [Amazon S3 Console](https://s3.console.aws.amazon.com/s3/get-started?region=ap-southeast-2) và chọn **Create bucket**
![Trang chủ S3 Console](/images/temp/1/8.png?featherlight=false&width=90pc)

2. Tại trang **Create bucket**, cấu hình các thông số sau:
   * Trong phần **Bucket settings for Block Public Access**:
     * Chọn **Bucket type**: General purpose
     * Nhập tên bucket: `book-image-stores-by-myself`
     * Chọn **ACLs disabled** cho Object Ownership
   ![Cấu hình bucket cơ bản](/images/temp/1/9.png?featherlight=false&width=90pc)
   * Trong phần **Block Public Access settings**:
     * Bỏ chọn **Block all public access**
     * Đánh dấu vào ô **I acknowledge that the current settings might result in this bucket and the objects within becoming public**
   ![Cấu hình quyền truy cập](/images/temp/1/10.png?featherlight=false&width=90pc)

3. Chọn **Create bucket** để hoàn tất quá trình tạo bucket
![Hoàn thành tạo bucket](/images/temp/1/11.png?featherlight=false&width=90pc)

4. Lặp lại các bước 1-3 để tạo bucket thứ hai với tên **book-image-resize-stores-by-myself**

### Cấu hình Lambda Trigger

5. Tại trang **resize-image** của Lambda function:
   * Chọn **Add Trigger**
![Thêm trigger](/images/temp/1/12.png?featherlight=false&width=90pc)

6. Tìm và chọn dịch vụ **S3** trong danh sách trigger
![Chọn S3 trigger](/images/temp/1/13.png?featherlight=false&width=90pc)

7. Tại trang cấu hình trigger:
   * Chọn bucket nguồn: **book-image-stores-by-myself**
   * Event type: Chọn **All object create events**
   * Đánh dấu vào ô xác nhận **I acknowledge...**
   * Chọn **Add** để hoàn tất
![Cấu hình S3 trigger](/images/temp/1/14.png?featherlight=false&width=90pc)

8. Kiểm tra kết quả cấu hình trigger cho Lambda function
![Xác nhận cấu hình trigger](/images/temp/1/15.png?featherlight=false&width=90pc)