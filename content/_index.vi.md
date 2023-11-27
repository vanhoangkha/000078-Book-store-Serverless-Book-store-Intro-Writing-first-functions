---
title : "Book Store - Giới thiệu Serverless Book store - Viết Lambda function"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
---
# Book Store - Giới thiệu Serverless Book store - Viết function

### Tổng quan

Đây là series giúp bạn tìm hiểu về Serverless với AWS Cloud. AWS cung cấp các công nghệ để chạy code, quản lý dữ liệu, và tích hợp các ứng dụng mà không cần quản lý máy chủ. Các công nghệ đó phục vụ cho người dùng tạo các ứng dụng theo mô hình Serverless. Các ứng dụng Serverless bắt đầu với AWS Lambda, lưu dữ liệu với DynamoDB, nhận yêu cầu của người dùng với API Gateway, host static web với S3/AWS Amplify Console,....

Trong series này, bạn sẽ đi từ các bước đầu tiên để xây dựng một ứng dụng web lưu thông tin sách bằng các dịch vụ Serverless của AWS. Ứng dụng cho phép người dùng đăng ký, đăng nhập, xem danh sách các loại sách và thêm vào giỏ hàng. Sau đó người dùng có thể xem giỏ hàng và checkout. Đối với người dùng là admin, admin được quyền thêm, sửa, xoá sách, quản lý và xử lý các đơn hàng. Dưới đây là toàn bộ series:

- [Giới thiệu Serverless Book Store - Viết Lambda Functions](https://000078.awsstudygroup.com)
- [Gọi API từ Front-end](https://000079.awsstudygroup.com)
- [Triển khai ứng dụng với SAM (Serverless Application Model)](https://000080.awsstudygroup.com)
- [Xác thực AWS Cognito](https://000081.awsstudygroup.com)
- [Cài đặt ACM, Route 53 và CloudFront](https://000082.awsstudygroup.com)
- [Đặt hàng với SQS và SNS](https://000083.awsstudygroup.com)
- [Triển khai CI/CD với CodePipeline](https://000084.awsstudygroup.com)
- [Theo dõi và giám sát với XRay và CloudWatch](https://000083.awsstudygroup.com)

Dưới đây là kiến trúc tổng quan của ứng dụng Book Store:
![SeverlessExample](/images/serverless-diagram.png)

- Tạo bảng với AWS DynamoDB để lưu thông tin của sách và S3 bucket lưu các tệp ảnh.
- Tạo các Lambda function để trigger bảng trong DynamoDB và S3 bucket.
- Sử dụng AWS SNS để gửi thông báo cho admin mỗi khi có một đơn hàng được đặt.
- Lưu các order vào queue với AWS SQS để quản lý.
- Đăng ký, đăng nhập và xác thực người dùng với AWS Cognito.
- Tạo, publish APIs với AWS API Gateway


Trong bài đầu tiên của series này, chúng ta sẽ tìm hiểu các khái niệm cơ bản về Serverless và thực hành tạo các function với Lambda được trigger từ S3 và ghi dữ liệu vào bảng DynamoDB. 
### Nội dung

 1. [Giới thiệu](1-introduce/)
 2. [Tạo Lambda thay đổi kích thước ảnh](2-resize-image-function/)
 3. [Tạo Lambda ghi dữ liệu vào DynamoDB](3-write-data-to-dynaomodb/)
