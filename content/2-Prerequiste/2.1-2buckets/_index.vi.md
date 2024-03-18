---
title: "Tạo 2 bucket"
date: "`r Sys.Date()`"
weight: 1
chapter: true
pre: " <b> 2.1 </b> "
---

### Tạo 2 bucket

1. Truy cập vào **AWS Management Console**, tìm **S3** và chọn **S3**.

![S3console](/images/2.prerequisite/20.png)

2. Trong giao diện **S3**, chọn **Create bucket**.

![CreateBucket](/images/2.prerequisite/21.png)

3. Trong giao diện create bucket:

- Mục **AWS Region**, chọn **Asia Pacific (Singapore) ap-southeast-1**.
- Mục **Bucket name**, nhập **`logging-workshop`**.

![CreateBucket](/images/2.prerequisite/22.png)

4. Tiếp tục:

- Mục **Block Public Access settings for this bucket**, bỏ chọn **Block all public access**.
- Mục **Turning off block all public access might result in this bucket and the objects within becoming public**, xác nhận mục này.

![CreateBucket](/images/2.prerequisite/23.png)

5. Kéo xuống dưới cùng, chọn **Create bucket**.

![CreateBucket](/images/2.prerequisite/24.png)

6. Xác nhận bucket đã được tạo thành công.

![CreateBucket](/images/2.prerequisite/25.png)

7. Tiếp tục tạo bucket **logging-workshop-destination**

- Mục **AWS Region**, chọn **Asia Pacific (Singapore) ap-southeast-1**.
- Mục **Bucket name**, nhập **`logging-workshop-destination`**.
- Không cần bỏ chọn mục **Block Public Access settings for this bucket**.
- Kéo xuống dưới cùng, chọn **Create bucket**.
- Xác nhận bucket đã được tạo thành công.

![CreateBucket](/images/2.prerequisite/39.png)
![CreateBucket](/images/2.prerequisite/40.png)
![CreateBucket](/images/2.prerequisite/41.png)
