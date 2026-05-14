---
title: "Xử lý và Tối ưu Kích thước Ảnh trên AWS"
date: 2024-01-01
weight: 2
chapter: false
pre: "<b> 2. </b>"
---

### Giới thiệu

Trong bài lab này, chúng ta sẽ xây dựng một giải pháp tự động xử lý ảnh sử dụng AWS Lambda với Node.js runtime. Ứng dụng sẽ tự động điều chỉnh kích thước ảnh khi được tải lên Amazon S3, lưu trữ phiên bản đã tối ưu vào một S3 bucket riêng biệt, và quản lý vòng đời của ảnh gốc.

### Các bước thực hiện

1. [Thiết lập AWS Lambda Function](2-1-create-lambda-function/)
   - Tạo Lambda function với Node.js 18.x runtime
   - Cấu hình môi trường và dependency
   - Triển khai mã nguồn xử lý ảnh

2. [Khởi tạo Amazon S3 Bucket](2-2-create-s3-bucket/)
   - Tạo bucket nguồn cho ảnh gốc
   - Tạo bucket đích cho ảnh đã xử lý
   - Cấu hình policy và quyền truy cập

3. [Thiết lập IAM Role và Policy](2-3-create-policy-access-s3/)
   - Tạo IAM Role cho Lambda function
   - Cấu hình policy cho phép truy cập S3
   - Áp dụng các best practice về bảo mật

4. [Kiểm thử và Xác thực](2-4-test-lambda-function/)
   - Thử nghiệm quy trình xử lý ảnh
   - Kiểm tra logs và monitoring
   - Xác nhận kết quả tối ưu

### Yêu cầu tiền quyết

- Tài khoản AWS với quyền truy cập đầy đủ
- Kiến thức cơ bản về AWS Lambda và S3
- Hiểu biết về Node.js và xử lý ảnh

### Tham khảo

- [AWS Lambda Developer Guide](https://docs.aws.amazon.com/lambda/)
- [Amazon S3 Developer Guide](https://docs.aws.amazon.com/s3/)
- [AWS SDK for JavaScript](https://aws.amazon.com/sdk-for-javascript/)