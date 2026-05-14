
---
title: "Tạo và Quản lý Bảng trong AWS DynamoDB"
date: 2024-01-01
weight: 1
chapter: false
pre: "<b> 3.1 </b>"
---

#### Hướng dẫn Tạo Bảng DynamoDB

#### Truy cập AWS Console

1. Truy cập vào [AWS Management Console](https://console.aws.amazon.com) và điều hướng đến dịch vụ DynamoDB
2. Trong giao diện DynamoDB Dashboard, chọn **Create table**

![Giao diện DynamoDB Console](/images/temp/1/35.png?width=90pc)

#### Cấu hình Bảng Cơ bản

1. Thiết lập thông tin bảng:
   - Nhập tên bảng: **Books**
   - Định nghĩa partition key: **id** (khóa chính)

![Cấu hình thông tin bảng](/images/temp/1/36.png?width=90pc)

#### Tùy chỉnh Cài đặt Nâng cao

1. Trong phần **Table settings**, chọn **Customize settings**
2. Cấu hình các thông số:
   - **Table class**: Chọn DynamoDB Standard
   - **Capacity mode**: Chọn On-demand (Theo nhu cầu)

![Cấu hình capacity](/images/temp/1/37.png?width=90pc)

#### Hoàn tất Tạo Bảng

1. Kiểm tra lại tất cả cấu hình
2. Chọn **Create table** để hoàn tất quá trình

![Hoàn thành tạo bảng](/images/temp/1/38.png?width=90pc)

#### Lưu ý Quan trọng

- Chế độ On-demand phù hợp với workload không đều hoặc khó dự đoán
- Partition key là bắt buộc và không thể thay đổi sau khi tạo bảng
- Bạn có thể thêm các index phụ sau khi tạo bảng

