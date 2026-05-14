---
title: "Giới thiệu"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1. </b> "
---

#### Tổng quan

Trước khi bắt đầu tìm hiểu về việc phát triển các hàm Lambda, chúng ta hãy tìm hiểu về kiến trúc Serverless và dịch vụ AWS Lambda.

#### Serverless

Serverless là mô hình điện toán đám mây trong đó các dịch vụ được quản lý hoàn toàn bởi AWS. Khi sử dụng các dịch vụ Serverless, người dùng không cần quan tâm đến:

- Quản lý và bảo trì hạ tầng
- Cập nhật bản vá bảo mật
- Quản lý tài nguyên hệ thống
- Khả năng mở rộng hệ thống

AWS cung cấp nhiều dịch vụ Serverless như:
- Điện toán: AWS Lambda
- Cơ sở dữ liệu: Amazon Aurora Serverless v2, Amazon DynamoDB
- Phân tích dữ liệu: Amazon Redshift Serverless
- Container: AWS Fargate

#### AWS Lambda

AWS Lambda là dịch vụ điện toán Serverless cho phép chạy mã nguồn mà không cần quản lý máy chủ. Các ưu điểm chính của Lambda bao gồm:

- Tự động mở rộng theo nhu cầu sử dụng
- Chỉ tính phí khi code thực sự chạy
- Hỗ trợ nhiều ngôn ngữ lập trình phổ biến
- Tích hợp sẵn với các dịch vụ AWS khác
- Bảo mật và cô lập môi trường thực thi

Lambda function là đơn vị thực thi cơ bản trong AWS Lambda. Mỗi function có thể:
- Xử lý từ vài request đến hàng nghìn request mỗi giây
- Tự động scale theo tải
- Tích hợp với nhiều trigger khác nhau (API Gateway, S3, DynamoDB, etc.)
- Thực thi trong môi trường an toàn và độc lập

Trong phần tiếp theo, chúng ta sẽ tạo Lambda function đầu tiên để xử lý hình ảnh với các chức năng:
- Thay đổi kích thước ảnh khi upload lên S3 bucket
- Lưu ảnh đã xử lý vào bucket mới
- Xóa ảnh gốc sau khi xử lý thành công