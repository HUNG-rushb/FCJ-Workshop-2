---
title: "Logging với AWS CloudTrail"
date: "`r Sys.Date()`"
weight: 4
chapter: false
pre: " <b> 4. </b> "
---

- Cách hoạt động của CloudTrail bao gồm 3 thành phần chính:
  - **Event** là record về một hoạt động trong tài khoản AWS.
  - **Trail** cho phép CloudTrail phân phối log tới bucket Amazon S3, CloudWatch log và CloudWatch event.
  - **Log bucket** dùng để lưu trữ các file log.

### Kích hoạt Server access logging

1. Trong giao diện **AWS Console**, tìm và chọn **Cloudtrail**.

2. Chọn **Create trail**

3. Thực hiện:

- Mục **Trail name**, nhập **`S3_logging_workshop`**.
- Mục **Trail log bucket and folder**, nhập **`aws-cloud-trail-logs-workshop`**.
- Mục **Log file SSE-KMS encryption**, bỏ tick **Enable**.

4. Kéo xuống dưới và chọn **Next**.

5. Tại mục **Event type**, tick chọn thêm **Data events**.

6. Kéo xuống dưới, tại mục **Data events**, chọn **S3**. Sau đó nhấn **Next**.

7. Review lại và ấn **Create trail**.

8. Kiểm tra trail đã được tạo thành công.

9. Quay trở về giao diện **S3 console**, chúng ta có thể thấy bucket **aws-cloud-trail-logs-workshop** đã được tạo ra để lưu log.

10. Mở một tab ẩn danh mới và nhập URL truy cập tới file chúng ta đã lưu.

11. Chờ khoảng 10 phút, sau đó refresh. Truy cập vào các folder bên trong cho tới khi chúng ta có thể thấy các file log đã được tạo ra.

12. Chọn vào 1 file log bất kỳ, ấn **Download**.

13. Khi xem file log đã được tải về, ta có thể thấy nội dung có dạng JSON như sau:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "ecr-public:GetAuthorizationToken",
        "sts:GetServiceBearerToken",
        "ecr-public:BatchCheckLayerAvailability",
        "ecr-public:GetRepositoryPolicy",
        "ecr-public:DescribeRepositories",
        "ecr-public:DescribeRegistries",
        "ecr-public:DescribeImages",
        "ecr-public:DescribeImageTags",
        "ecr-public:GetRepositoryCatalogData",
        "ecr-public:GetRegistryCatalogData"
      ],
      "Resource": "*"
    }
  ]
}
```
