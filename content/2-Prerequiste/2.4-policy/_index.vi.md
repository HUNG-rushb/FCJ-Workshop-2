---
title: "Thêm policy cho bucket"
date: "`r Sys.Date()`"
weight: 4
chapter: true
pre: " <b> 2.4 </b> "
---

### Thêm policy cho bucket

1. Trở về giao diện S3, chọn **logging-workshop** bucket.

2. Trong giao diện bucket, chọn mục **Permissions**.

3. Mục **Bucket policy**, chọn **Edit**.

4. Nhập vào mục policy:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::logging-workshop/*"
    }
  ]
}
```

5. Kéo xuống dưới cùng, chọn **Save changes**

6. Xác nhận update policy thành công.
