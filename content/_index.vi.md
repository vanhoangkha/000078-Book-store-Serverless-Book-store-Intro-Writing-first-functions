---
title: "Serverless - Tương tác giữa Lambda với S3 và DynamoDB"
date: "2025-01-22"
weight: 1
chapter: false
---

# Serverless - Tương tác giữa Lambda với S3 và DynamoDB

### Tổng quan

Đây là phần trong chuỗi bài viết về Serverless trên AWS Cloud. AWS cung cấp nhiều dịch vụ hiện đại cho phép bạn chạy code, quản lý dữ liệu và tích hợp ứng dụng mà không cần quản lý hạ tầng máy chủ. Những công nghệ này cho phép xây dựng ứng dụng theo mô hình Serverless hoàn chỉnh. Một ứng dụng Serverless điển hình sẽ sử dụng AWS Lambda để xử lý logic, DynamoDB để lưu trữ dữ liệu, Amazon API Gateway để xử lý request từ người dùng, và S3/AWS Amplify để host ứng dụng web tĩnh.

Dưới đây là kiến trúc mẫu của một ứng dụng web Serverless trên AWS Cloud:
![KienTrucServerless](/images/Arch-Diagrams_Serverless-Category-Page_WebApp.png?featherlight=false&width=90pc)

Trong phần đầu tiên của chuỗi bài này, chúng ta sẽ tìm hiểu về:
- Các khái niệm nền tảng của Serverless Computing
- Thực hành xây dựng Lambda function được kích hoạt bởi sự kiện từ S3
- Cách tương tác và lưu trữ dữ liệu vào DynamoDB thông qua Lambda

### Nội dung

1. [Tổng quan về Serverless trên AWS](1-introduce/)
   - Kiến trúc Serverless
   - Các thành phần chính: Lambda, S3, DynamoDB
   - Use cases phổ biến

2. [Xây dựng Lambda Function xử lý ảnh](2-resize-image-function/)
   - Tạo và cấu hình Lambda function
   - Thiết lập trigger từ S3
   - Xử lý resize ảnh với Lambda Layers
   - Best practices về bảo mật và tối ưu

3. [Lambda và tương tác với DynamoDB](3-write-data-to-dynamodb/)
   - Tạo bảng DynamoDB với partition key và sort key
   - Cấu hình IAM roles và permissions
   - Thao tác CRUD cơ bản với DynamoDB SDK
   - Monitoring và troubleshooting

