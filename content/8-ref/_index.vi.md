---
title: "Dọn dẹp tài nguyên"
date: "`r Sys.Date()`"
weight: 6
chapter: false
pre: " <b> 6. </b> "
---

Chúng ta sẽ tiến hành các bước sau để xóa các tài nguyên chúng ta đã tạo trong bài thực hành này.

### Xóa Athena query

1. Tìm và chọn service **Athena**, sau đó chọn **Launch query editor**, chọn tab **Settings**, ấn **Manage**.

2. Ấn _X_ để xóa bucket lưu query, ấn **Save**.

### Xóa CloudTrail

3. Tìm và chọn service **CloudTrail**, chọn **Trails** ở bảng điều hướng bên trái. Chọn trail **S3_logging_workshop**, sau đó chọn **Delete**.

4. Xác nhận **Delete**.

### Xóa S3 buckets

5. Tìm và chọn service **S3**, sau chọn chọn bucket **logging_workshop**. Để xóa bucket ta cần xóa tất cả các file trong bucket đó. Chọn tất cả cái file sau đó ấn **Delete**.

6. Xác nhận để xóa tất cả các file. Ấn **Delete objects**.

7. Quay trở về danh sách bucket, và chọn bucket **logging_workshop**, chọn **Delete**.

8. Xác nhận tên bucket và ấn **Delete bucket**.

9. Lặp lai các bước từ bước 5 để xóa objects và xóa bucket cho 2 bucket còn lại, **logging-workshop-destinations** và **aws-cloudtrail-log-workshop**.
