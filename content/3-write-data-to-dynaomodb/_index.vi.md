
---
title: "Ghi dữ liệu vào Amazon DynamoDB"
date: 2024-01-01
weight: 3
chapter: false
pre: " <b> 3. </b> "
---

Trong phần này, chúng ta sẽ thực hiện việc tạo và quản lý dữ liệu với Amazon DynamoDB thông qua AWS Lambda function sử dụng Python. Chúng ta sẽ tìm hiểu cách xây dựng một giải pháp serverless để lưu trữ và xử lý dữ liệu một cách hiệu quả.

### Tổng quan

Amazon DynamoDB là một cơ sở dữ liệu NoSQL được quản lý hoàn toàn bởi AWS, cung cấp hiệu suất cao và khả năng mở rộng tự động. Kết hợp với AWS Lambda, chúng ta có thể xây dựng các ứng dụng serverless mạnh mẽ.

### Nội dung

1. [Khởi tạo và cấu hình bảng trong Amazon DynamoDB](3-1-create-dynamodb-table/)
   - Thiết kế cấu trúc bảng
   - Cấu hình partition key và sort key
   - Thiết lập capacity mode

2. [Phát triển Lambda function để ghi dữ liệu](3-2-write-data-by-lambda/)
   - Tạo Lambda function với Python runtime
   - Cấu hình IAM role và permissions
   - Triển khai logic ghi dữ liệu
   - Kiểm thử và tối ưu hiệu suất

