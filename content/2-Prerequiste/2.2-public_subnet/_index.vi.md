---
title: "Tạo Public subnet"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 2.2 </b> "
---

1. Chuyển tới **VPC** console, và quan sát xem bạn đã có **Default VPC** hay chưa.

![FCJ_ws2](/images/2.prerequisite/2.png)

2. Chọn **Subnets** tại bảng điều hướng bên trái, chọn **Create subnet**.

![FCJ_ws2](/images/2.prerequisite/3.png)

3. Chọn **Default VPC**.

![FCJ_ws2](/images/2.prerequisite/4.png)

4. Tạo subnet 1:

- Mục **Subnet name**, nhập **`fcj-subnet-1`**.
- Mục **Availability zone**, chọn **`us-east-1a`**.
- Mục **IPv4 subnet CIDR block**, nhập **`172.31.200.0/24`**.

![FCJ_ws2](/images/2.prerequisite/5.png)

5. Chọn **Add new subnet**, và tạo subnet 2:

- Mục **Subnet name**, nhập **`fcj-subnet-1`**.
- Mục **Availability zone**, chọn **`us-east-1b`**.
- Mục **IPv4 subnet CIDR block**, nhập **`172.31.201.0/24`**.

![FCJ_ws2](/images/2.prerequisite/6.png)

1. Chọn **Add new subnet**, và tạo subnet 3:

- Mục **Subnet name**, nhập **`fcj-subnet-1`**.
- Mục **Availability zone**, chọn **`us-east-1c`**.
- Mục **IPv4 subnet CIDR block**, nhập **`172.31.202.0/24`**.
- Chọn **Create subnet**.

![FCJ_ws2](/images/2.prerequisite/7.png)

7. Xác nhận 3 subnet đã được tạo thành công.

![FCJ_ws2](/images/2.prerequisite/8.png)
