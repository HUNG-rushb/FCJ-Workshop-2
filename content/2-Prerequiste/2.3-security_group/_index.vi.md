---
title: "Tạo Security group"
date: "`r Sys.Date()`"
weight: 3
chapter: false
pre: " <b> 2.3 </b> "
---

<!-- - Tải xuống file **S3_logging_workshop.txt** tại {{%attachments  pattern=".txt"/%}}  -->

### Tạo Security group

1. Chuyển tới **Security Groups**, chọn **Create security group**.

![FCJ_ws2](/images/2.prerequisite/9.png)

2. Tạo security group:

- Mục **Security group name**, nhập **`FCJ_SG`**.
- Mục **Description**, nhập **`Allow inbound HTTP on port 80`**.
- Mục **VPC**, chọn **Default VPC**.
- Mục **Inbound rules**, chọn **Add rule**, **Type** chọn **HTTP**, **Source** chọn **Anywhere-IPv4**.
- Kéo xuống dưới cùng, chọn **Create security group** (không có trong hình).

  ![FCJ_ws2](/images/2.prerequisite/10.png)
