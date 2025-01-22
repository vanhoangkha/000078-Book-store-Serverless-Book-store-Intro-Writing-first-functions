
---
title: "Kiểm tra hoạt động của Lambda Function"
date: "`r Sys.Date()`"
weight: 4
chapter: false
pre: " <b> 2.4 </b> "
---

### Tải lên và kiểm tra ảnh trong S3 Bucket

1. Truy cập S3 Bucket **book-image-stores-by-myself**:
   - Nhấn vào nút **Upload** để bắt đầu quá trình tải lên
   ![Tải lên S3](/images/temp/1/27.png?width=90pc)

2. Trong giao diện **Upload**:
   - Chọn **Add files** để thêm tệp
   - Chọn tệp ảnh cần tải lên và nhấn **Upload**
   ![Giao diện Upload](/images/temp/1/28.png?width=90pc)

3. Chờ Lambda Function xử lý:
   - Sau khi tải lên, đợi Lambda Function hoàn thành xử lý
   - Kiểm tra xem ảnh gốc đã được di chuyển
   ![Kiểm tra xử lý](/images/temp/1/29.png?width=90pc)

### Truy cập ảnh đã xử lý

4. Mở S3 Bucket đích **book-image-resize-stores-by-myself**:
   - Tìm và chọn tệp ảnh đã được xử lý
   ![Truy cập ảnh](/images/temp/1/30.png?width=90pc)

5. Truy cập ảnh:
   - Nhấn vào **Object URL** để tải ảnh
   ![Object URL](/images/temp/1/31.png?width=90pc)

6. Xử lý lỗi truy cập:
   - Bạn sẽ nhận được thông báo **Access Denied**
   ![Lỗi truy cập](/images/temp/1/32.png?width=90pc)

### Cấu hình quyền truy cập Bucket

7. Thiết lập chính sách Bucket:
   - Quay lại cấu hình Bucket, chọn tab **Permissions**
   - Nhấn **Edit** trong phần Bucket policy
   ![Chỉnh sửa policy](/images/temp/1/33.png?width=90pc)
   - Thêm JSON policy sau:
   ```json
   {
       "Version": "2012-10-17",
       "Statement": [
           {
               "Sid": "PublicReadGetObject",
               "Effect": "Allow",
               "Principal": "*",
               "Action": "s3:GetObject",
               "Resource": "arn:aws:s3:::book-image-resize-stores-by-myself/*"
           }
       ]
   }
   ```
   - Nhấn **Save changes** để lưu chính sách
   ![Lưu policy](/images/temp/1/34.png?width=90pc)

8. Xác nhận hoạt động:
   - Thử lại các bước 6 và 7 để tải ảnh
   - So sánh ảnh đã tải về với ảnh gốc để kiểm tra kết quả resize
   - Lambda Function resize đã hoạt động thành công