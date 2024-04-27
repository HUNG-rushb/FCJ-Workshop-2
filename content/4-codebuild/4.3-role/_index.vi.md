---
title: "Cập nhật quyền cho codebuild role"
date: "`r Sys.Date()`"
weight: 3
chapter: false
pre: " <b> 4.3 </b> "
---

### Cập nhật quyền cho codebuild role

1. Truy cập tới dịch vụ **IAM**:

- Ở menu bên trái, chọn **Roles**.
- Nhập tìm **`codebuild`**.
- Chọn role codebuild tương ứng với project của bạn.

![FCJ_ws2](/images/4.codebuild/21.png)

2. Chọn **Add permissions**, sau đó **Create inline policy**.

![FCJ_ws2](/images/4.codebuild/22.png)

3. Copy và paste policy dưới đây vào **Policy editor**. Sau đó kéo xuống dưới chọn **Next**.

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

![FCJ_ws2](/images/4.codebuild/23.png)

4. Mục **Policy name**, nhập **FCJ_ECR_Public_Access**. Sau đó nhấn **Create policy**.

![FCJ_ws2](/images/4.codebuild/24.png)

5. Xác nhận policy đã được thêm thành công.

![FCJ_ws2](/images/4.codebuild/25.png)

6. Tiếp tục chọn **Add permissions**, sau đó **Attach policies**.

![FCJ_ws2](/images/4.codebuild/26.png)

7. Nhập tìm **AmazonEC2ContainerRegistryFullAccess**. Chọ và nhấn **Add permissions**.

![FCJ_ws2](/images/4.codebuild/27.png)

8. Xác nhận policy đã được thêm thành công.

![FCJ_ws2](/images/4.codebuild/28.png)
