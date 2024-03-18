---
title: "Cập nhật quyền tạo log"
date: "`r Sys.Date()`"
weight: 2
chapter: true
pre: " <b> 2.2 </b> "
---

### Cập nhật quyền tạo log cho S3 log delivery group

1. Quay về giao diện các bucket, chọn bucket **logging-workshop-destination**. Kéo xuống mục **Object Ownership**, chọn **Edit**

![CreateBucket](/images/2.prerequisite/41-5.png)
![CreateBucket](/images/2.prerequisite/42.png)

2.  Chọn **ACLs enabled**, xác nhận **I acknowledge that ACLS will be restored.**, nhấn **Save changes**. Bước này sẽ giúp những đối tượng trong **Access control list (ACL)** ngoài bucket owner có quyền tạo object.

![CreateBucket](/images/2.prerequisite/43.png)

3. Sau đó kéo xuống mục **Access control list (ACL)**, chọn **Edit**.

![CreateBucket](/images/2.prerequisite/44.png)

4. Tại mục **S3 log delivery group**, chọn quyền **Write**, sau đó **Save changes**.

![CreateBucket](/images/2.prerequisite/45.png)

5. Xác nhận quyền **Write** cho **S3 log delivery group**.

![CreateBucket](/images/2.prerequisite/46.png)

6. Trở vê giao diện các bucket.
