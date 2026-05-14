---
title: "Tạo Lambda Function để Ghi dữ liệu"
date: 2024-01-01
weight: 2
chapter: false
pre: "<b> 3.2 </b>"
---

### Tạo Lambda Function mới

1. Truy cập [AWS Lambda Console](https://console.aws.amazon.com/lambda)
   - Chọn **Functions** từ thanh điều hướng bên trái
   - Nhấn nút **Create function**

![Tạo Lambda Function](/images/temp/1/39.png)

2. Trong trang **Create function**:
   - Chọn **Author from scratch** 
   - Đặt tên function: **book_create**
   - Chọn **Python 3.11** làm Runtime
   - Nhấn **Create function**

![Cấu hình Lambda Function](/images/temp/1/40.png)

### Cấu hình Function

3. Trong giao diện function **book_create**:
   - Paste code sau vào editor **lambda_function.py**:

```python
import boto3
import json

client = boto3.resource('dynamodb')
    
def lambda_handler(event, context):
    book_item = event["body"]
    error = None
    
    try:
        table = client.Table('Books')
        table.put_item(Item = book_item)
    except Exception as e:
        error = e
        
    if error is None:
        response = {
            'statusCode': 200,
            'body': 'Ghi dữ liệu vào DynamoDB thành công!',
            'headers': {
                'Content-Type': 'application/json'
            },
        }
    else:
        response = {
            'statusCode': 400,
            'body': 'Ghi dữ liệu vào DynamoDB thất bại!',
            'headers': {
                'Content-Type': 'application/json'
            },
        }

    return response
```

   - Nhấn **Deploy** để lưu thay đổi

![Cấu hình Code](/images/temp/1/41.png)

### Cấu hình IAM Permissions

4. Thêm quyền truy cập DynamoDB:
   - Chọn tab **Configuration**
   - Chọn **Permissions** từ menu trái
   - Nhấn vào role của function

![Cấu hình IAM](/images/temp/1/42.png)

5. Trong trang IAM Role:
   - Chọn **Attach policies**
   - Tìm và chọn policy **AmazonDynamoDBFullAccess**
   - Nhấn **Add permissions**

![Thêm Policy](/images/temp/1/43.png)

### Kiểm tra Function

6. Tạo test event:
   - Chọn tab **Test**
   - Đặt tên event: **test_1** 
   - Nhập JSON test sau:

```json
{
  "body": {
      "id": "1",
      "name": "Java Programming",
      "author": "Alex Smith",
      "category": "Technology",
      "price": "10.89",
      "description": "Hướng dẫn lập trình Java cơ bản",
      "image": "https://book-image-resize-store.s3.amazonaws.com/Java.jpg"
  }
}
```

   - Nhấn **Save** và **Test**

![Test Function](/images/temp/1/45.png)

### Xác nhận dữ liệu trong DynamoDB

7. Truy cập DynamoDB Console:
   - Chọn bảng **Books**
   - Chọn **Explore table items**

![Xem DynamoDB](/images/temp/1/47.png)

8. Kiểm tra dữ liệu đã được thêm vào:

![Kết quả](/images/temp/1/48.png)